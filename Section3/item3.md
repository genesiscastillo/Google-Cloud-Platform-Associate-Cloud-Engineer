

# 3.- Deploying and implementing a cloud solution

## 3.3 Deploying and implementing App Engine and Cloud Functions resources
---
### 3.3.1.- Deploying an application to App Engine

* Doc reference 
    - [An Overview of App Engine](https://cloud.google.com/appengine/docs/standard/java/an-overview-of-app-engine)
    - [How Instances are Managed](https://cloud.google.com/appengine/docs/standard/java/how-instances-are-managed)
    - [How to Configure and Deploy An Application on Google App Engine](https://www.gspann.com/resources/blogs/how-to-configure-and-deploy-an-application-on-google-app-engine/)
    - [Building an App on App Engine](https://cloud.google.com/appengine/docs/standard/java/building-app)

> The App Engine is a fully-managed platform as a service (PaaS) for building web applications in which the user doesn’t need to manage the underlying operating systems, configurations, security issues, firewalls, and auto-scaling. By using this service, developers can manage the entire application just by making a configuration file called app.yaml to make the code compatible with the App Engine.

![App Engine](https://cloud.google.com/appengine/docs/images/modules_hierarchy.svg)


> The App Engine is based on serverless architecture. It is available with two types of runtime environments:
> * **Standard environment**: It supports only a few languages, including Python, Node js, Go, PHP, .Net, Java. To deploy a Python application, it requires a standard environment along with a configuration file that defines our runtime environment in the file app.yaml.
> * **Flexible environment**: It supports all kinds of applications and provides some control over the infrastructure. It uses Docker containers as a resource to run the application. Besides the supported runtimes, it can also make custom runtime using a Dockerfile.

> The App Engine does not understand the source code for deployment. The source code needs to be refactored with the configuration file called app.yaml, where it’s important to mention the runtime and scaling details

> - Runtime environment: Mention the source-code runtime here so that the App Engine can set up an environment to support and deploy the code for public usage.
> - Scaling information: Provide the information of scaling here, like what type of scaling is required to use for the application (automatic/basic/manual), how many instances will be available while scaling, and on how can it scales the application (on CPU utilization/concurrent requests/latency).
> - Resources information: Mention the number of CPUs, memory_gb (RAM), and disk_size available for the application.
> - Environment variables: Provide environment variables for the application, like passwords, API keys, etc., so that the application can use them securely.

*sample app.yaml*
```yaml
service: my-service
runtime: nodejs10
instance_class: B8

automatic_scaling:
  target_cpu_utilization: 0.6
  min_instances: 1
  max_instances: 15
cool_down_period_sec: 180
  min_pending_latency: 30ms  # default value
  max_pending_latency: automatic
  max_concurrent_requests: 50

env_variables:
  BUCKET_NAME: "example-gcs-bucket"

network:
  instance_tag: TAG_NAME
  name: NETWORK_NAME
  subnetwork_name: SUB_NETWORK_NAME
  forwarded_ports:
	- PORT
	- HOST_PORT: CONTAINER_PORT
	- PORT/tcp
	- HOST_PORT: CONTAINER_PORT/udp

resources:
  cpu: 2
  memory_gb: 2.3
  disk_size_gb: 10
  volumes:
    - name: ramdisk1
      volumem_type: tmpfs
      size_gb: 0.5

liveness_check:
  path: "/liveness_check"
  check_interval_sec: 30
  timeout_sec: 4
  failure_threshold: 2
  success_threshold: 2

```
#### **scaling configuration**
App Engine supports the following scaling types, which controls how and when instances are created:

- **Automatic**
Automatic scaling creates instances based on request rate, response latencies, and other application metrics. You can specify thresholds for each of these metrics, as well as a minimum number instances to keep running at all times

- **Basic**
Basic scaling creates instances when your application receives requests. Each instance will be shut down when the application becomes idle. Basic scaling is ideal for work that is intermittent or driven by user activity

- **Manual**
Basic scaling creates instances when your application receives requests. Each instance will be shut down when the application becomes idle. Basic scaling is ideal for work that is intermittent or driven by user activity

#### **SERVICES**
Utiliza los servicios de App Engine para `factorizar tus apps grandes en componentes lógicos que puedan compartir características de App Engine de forma segura y comunicarse entre sí`. En general, los servicios de App Engine se comportan como microservicios. Por lo tanto, puedes ejecutar tu app en un solo servicio o puedes diseñar e implementar varios servicios para que se ejecuten como un conjunto de microservicios.

Por ejemplo, una aplicación que controla las solicitudes de los clientes podría incluir servicios separados, y cada uno controlar diferentes tareas, como:

- Solicitudes a la API desde dispositivos móviles
- Solicitudes de administración internas
- Procesamiento de backend, como canalización de facturación y análisis de datos

Cada servicio de App Engine consta del código fuente de tu app y los archivos de configuración de App Engine correspondientes. El conjunto de archivos que implementas en un servicio representa una sola versión de ese servicio, y cada vez que implementas en ese servicio creas versiones adicionales dentro de este.

#### **VERSIONS**
Tener varias versiones de tu app en cada servicio te permite alternar rápidamente de versión para reversiones, pruebas o distintos eventos temporales. Puedes enrutar tráfico a una o más versiones específicas de la app mediante la migración o división del tráfico.

> The App Engine makes the application deployment process easy and fast. It can deploy the application by just typing "gcloud app deploy app.yaml." Also, it can have multiple versions for each service and seamlessly migrating traffic from one version to another in the App Engine by using a flag – ‘migrate.’ It can deploy and route the entire traffic to the latest version of the application with zero downtime
```bash
    gcloud app services set-traffic [MY_SERVICE] --splits [MY_VERSION]=2 --migrate
```
#### **TRAFFIC SPLITTING**
You can use traffic splitting `to specify a percentage distribution of traffic across two or more of the versions within a service`. Splitting traffic allows you to conduct A/B testing between your versions and provides control over the pace when rolling out features.

Traffic splitting is applied to URLs that do not explicitly target a version. For example, the following URLs split traffic because they target all the available versions within the specified service:

- *https://PROJECT_ID.REGION_ID.r.appspot.com*
    - Distributes traffic to versions of the default service.
- *https://SERVICE_ID-dot-PROJECT_ID.REGION_ID.r.appspot.com*
    - Distributes traffic to versions of the [SERVICE_ID] service.
---

### 3.3.2.- Deploying a Cloud Function that receives Google Cloud events

#### Cloud Pub/Sub events

```javascript
exports.helloPubSub = (message, context) => {
  const name = message.data
    ? Buffer.from(message.data, 'base64').toString()
    : 'World';

  console.log(`Hello, ${name}!`);
};
```
```bash
gcloud functions deploy helloPubSub \
--runtime nodejs10 \
--trigger-topic YOUR_TOPIC_NAME

gcloud pubsub topics create YOUR_TOPIC_NAME

gcloud pubsub topics publish YOUR_TOPIC_NAME --message YOUR_NAME

gcloud functions logs read --limit 50

gcloud functions delete helloPubSub 
```

- PLUS [operations are implemented in corresponding files and are mapped to HTTP verbs](https://github.com/GoogleCloudPlatform/deploymentmanager-samples/tree/master/google/resource-snippets/functions-backed-type/function)


#### Cloud Storage object change notification events

```javascript
exports.helloGCS = (file, context) => {
  console.log(`  Event: ${context.eventId}`);
  console.log(`  Event Type: ${context.eventType}`);
  console.log(`  Bucket: ${file.bucket}`);
  console.log(`  File: ${file.name}`);
  console.log(`  Metageneration: ${file.metageneration}`);
  console.log(`  Created: ${file.timeCreated}`);
  console.log(`  Updated: ${file.updated}`);
};
```
```bash
gcloud functions deploy helloGCS \
--runtime nodejs10 \
--trigger-resource YOUR_TRIGGER_BUCKET_NAME \
--trigger-event google.storage.object.finalize

gsutil cp gcf-test.txt gs://YOUR_TRIGGER_BUCKET_NAME

gcloud functions logs read --limit 50

gcloud functions deploy helloGCS \
--runtime nodejs10 \
--trigger-resource YOUR_TRIGGER_BUCKET_NAME \
--trigger-event google.storage.object.delete

gsutil versioning set off gs://YOUR_TRIGGER_BUCKET_NAME

gsutil cp gcf-test.txt gs://YOUR_TRIGGER_BUCKET_NAME

gsutil rm gs://YOUR_TRIGGER_BUCKET_NAME/gcf-test.txt

gcloud functions logs read --limit 50

gcloud functions delete helloGCS 
```

