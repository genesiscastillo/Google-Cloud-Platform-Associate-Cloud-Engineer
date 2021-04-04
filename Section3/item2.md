# 3.-  Deploying and implementing a cloud solution

## 3.2 Deploying and implementing Kubernetes Engine resources

* [Kubernetes Design and Architecture](https://github.com/kubernetes/community/blob/master/contributors/design-proposals/architecture/architecture.md)

---
### 3.2.1.- Deploying a Kubernetes Engine cluster


#### Creating a GKE cluster

The first step is to create a container cluster to run application workloads. The following command creates a new cluster with five nodes with the default machine type __(e2-medium)__:
```bash
gcloud components install kubectl

gcloud config set project project-id

gcloud config set compute/zone compute-zone

gcloud container clusters create cluster-name --num-nodes=1

gcloud container clusters get-credentials cluster-name
```
---
### 3.2.2.- Deploying a container application to Kubernetes Engine using pods

```bash
kubectl create deployment hello-server --image=gcr.io/google-samples/hello-app:1.0

kubectl expose deployment hello-server --type LoadBalancer \
  --port 80 --target-port 8080

kubectl get pods

kubectl get service hello-server

http://external-ip/
    
kubectl delete service hello-server

gcloud container clusters delete cluster-name

```
---
### 3.2.3.- Configuring Kubernetes Engine application monitoring and logging

#### **Deploying**
> To ingest logs, you must deploy the Stackdriver Logging agent to each node in your cluster. The agent is a configured fluentd instance, where the configuration is stored in a ConfigMap and the instances are managed using a Kubernetes DaemonSet. The actual deployment of the ConfigMap and DaemonSet for your cluster depends on your individual cluster setup

#### **Deploying to a new cluster GCP**
> Stackdriver is the default logging solution for clusters deployed on Google Kubernetes Engine. Stackdriver Logging is deployed to a new cluster by default unless you explicitly opt-out

#### **Configuring Stackdriver Logging Agents**
> Sometimes the default installation of Stackdriver Logging may not suit your needs, for example:
* You may want to add more resources because default performance doesn't suit your needs.
* You may want to introduce additional parsing to extract more metadata from your log messages, like severity or source code reference.
* You may want to send logs not only to Stackdriver or send it to Stackdriver only partially.
> To disable the default logging integration, use the following command:
```bash
gcloud beta container clusters update --logging-service=none <CLUSTER-NAME>
```

**Changing DaemonSet parameters**
> When you have the Stackdriver Logging DaemonSet in your cluster, you can just modify the template field in its spec, daemonset controller will update the pods for you.

```bash
kubectl get ds fluentd-gcp-v2.0 --namespace kube-system -o yaml > fluentd-gcp-ds.yaml

kubectl replace -f fluentd-gcp-ds.yaml
```

- Video
    * [Stack Driver Monitoring, Logging and Alerting on Google Cloud Kubernetes Engine](https://www.youtube.com/watch?v=oNEl-H0QWWg)

- Doc References
    * [Logging StackDriver](https://kubernetes.io/docs/tasks/debug-application-cluster/logging-stackdriver/)
    * [Monitoring Kubernetes Clusters on GKE](https://medium.com/google-cloud/gke-monitoring-84170ea44833)


**Autoscaling limits**

The total **size of this cluster is between three and twelve nodes**, spread across three zones. If one of the zones fails, the total size of cluster becomes between two and eight nodes.

```bash
gcloud container clusters create example-cluster \
  --zone us-central1-a \
  --node-locations us-central1-a,us-central1-b,us-central1-f \
  --num-nodes 2 --enable-autoscaling --min-nodes 1 --max-nodes 4
```