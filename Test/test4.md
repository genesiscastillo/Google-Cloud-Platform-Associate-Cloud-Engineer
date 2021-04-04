# Google Associate Cloud Engineer Practice 
# Exam Part - 5

1. You deployed a workload to your GKE cluster by running the command kubectl apply -f app.yaml. You also enabled a LoadBalancer service to expose the deployment by running kubectl apply – f service.yaml. Your pods are struggling due to increased load so you decided to enable horizontal pod autoscaler by running kubectl autoscale deployment [YOUR DEPLOYMENT] –cpu-percent=5t -min= 1 max=10. You noticed the autoscaler has launched several new pods but the new pods have failed with the message “Insuficient cpu”. What should you do to resolve thisissue?

    * A. Use “kubectl container clusters resize” to add more nodes to the node pool.
    * B. **Use “gcloud container clusters resize” to add more nodes to the node pool.**
    * C. Edit the managed instance group of the cluster and enable autoscaling.
    * D. Edit the managed instance group of the cluster and increase the number of VMs by 1.

10. Your organization is planning to deploy a Python web application to Google Cloud. The web application uses a custom Linux distribution and you want to minimize rework. The web application underpins an important website that is accessible to the customers globally. You have been asked to design a solution that scales to meet demand. What would you recommend to fulfull this requirement? (Select Two)__[REVISAR]__

    * A. Cloud Functions
    * B. App Engine Standard environment
    * C. **HTTP(S) Load Balancer**
    * D. **Managed Instance Group on Compute Engine**
    * E. Network Load Balance

12. The application development team at your company wants to use the biggest CIDR range possible for a VPC and has asked for your suggestion. Your operations team is averse to using any beta features. What should you suggest?__[REVISAR]__

    * A. Use 0.0.0.0/0 CIDR range.
    * B. **Use 10.0.0.0/8 CIDR range.**
        > The private network range is defined by IETF and adhered to by all cloud providers. The supported internal IP Address ranges are:
        >    1. 24-bit block 10.0.0.0/8 (__16.777.216 IP Addresses__)
        >    2. 20-bit block 172.16.0.0/12 (__1.048.576 IP Addresses__)
        >    3. 16-bit block 192.168.0.0/16 (__65.536 IP Addresses__)

        > __When you see a smaller number after the / , it means greater number of hosts.__
    * C. Use 172.16.0.0/12 CIDR range.
    * D. Use 192.168.0.0/16 CIDR range.

13. The storage costs for your application logs have far exceeded the project budget. The logs are currently being retained indefinitely in the Cloud Storage bucket myapp-gcp-ace-logs. You have been asked to remove logs older than 90 days from your Cloud Storage bucket. You want to optimize on going Cloud Storage spend. What should you do?

    * A. Write a script that runs gsutil Is -| – gs://myapp-gcp-ace-logs/** to find and remove items older than 90 days. Schedule the script with cron.
    * B. **Write a lifecycle management rule in JSON and push it to the bucket with gsutil lifecycleset config-json-file.**
    * C. Write a lifecycle management rule in XML and push it to the bucket with gsutil lifecycleset config-xml-file.
    * D. Write a script that runs gsutil Is -Ir gs://myapp-gcp-ace-logs/** to find and remove items older than 90 days. Repeat this process every morning.

14. Your company wants to migrate a mission-critical application to Google Cloud Platform. The application is currently hosted in your on-premises data centre and runs of several VMs. Your migration manager has suggested a “lift and shift” to Google Compute Engine Virtual Machines and has asked you to ensure the application scales quickly, automatically and eficiently based on the CPU utilization. You want to follow Google recommended practices. What should you do?

    * A. **Deploy the application to Google Compute Engine Managed Instance Group (MIG) with autoscaling enabled based on CPU utilization.**
    * B. Deploy the application to GKE cluster with Horizontal Pod Autoscaling (HPA) enabled based on CPU utilization.
    * C. Deploy the application to Google Compute Engine Managed Instance Group (MIG) with time-based autoscaling based on last months trafic patterns.
    * D. Deploy the application to Google Compute Engine Managed Instance Group (MIG). Deploy a Cloud Function to look up CPU utilization in Cloud Monitoring every minute andscale up or scale down the MIG group as needed.

15. Your company is migrating all applications from the on-premises data centre to Google Cloud,and one of the applications is dependent on Websockets protocol and session afinity. You want to ensure this application can be migrated to Google Cloud platform and continue serving requests without issues. What should you do?__[REVISAR]__

    * A. Modify application code to not depend on session afinity.
    * B. Review the design with the security team.
    * C. Modify application code to use HTTP streaming.
    * D. **Discuss load balancer options with the relevant teams.**

16. Your organization processes a very high volume of timestamped loT data. The total volume can be several petabytes. The data needs to be written and changed at a high speed. You want to use the most performant storage option for your data. Which product should you use?

    * A. **Cloud Bigtable**
    * B. Cloud Datastore
    * C. BigQuery
    * D. Cloud Storage

17. The deployment team currently spends a lot of time creating and configuring VMs in Google Cloud Console, and feel they could be more productive and consistent if the same can be automated using Infrastructure as Code. You want to help them identify a suitable service. What should you recommend?__[REVISAR]__

    * A. Managed Instance Group (MIG).
    * B. Unmanaged Instance Group.
    * C. **Deployment Manager.**
        ```yaml
        resources:
        - name: vm-created-by-deployment-manager
        type: compute.v1.instance
        properties:
            zone: us-central1-a
            machineType: zones/us-central1-a/machineTypes/n1-standard-1
            disks:
            - deviceName: boot
            type: PERSISTENT
            boot: true
            autoDelete: true
            initializeParams:
                sourceImage: projects/debian-cloud/global/images/family/debian-9
            networkInterfaces:
            - network: global/networks/default
        ```    
    * D. Cloud Build.

18. You work for a multinational consumer credit reporting company that collects and aggregates financial information and provides a credit report for over 100 million individuals and businesses.The company wants to trial a new application for a small geography and requires a relational database for storing important user information. Your company places a high value on reliability and requires point-in-time recovery while minimizing operational cost. What should you do?__[REVISAR]__

    * A. **Store the data in Cloud SQL for MySQL instance. Ensure Binary**
    * B. Logging on the Cloud SQL instance.
    * C. Store the data in a multi-regional Cloud Spanner instance.
    * D. Store the data in Highly Available Cloud SQL for MySQL instance.
    * E. Store the data in a 2-node Cloud Spanner instance.

19. Your company owns a mobile game that is popular with users all over the world. The mobile game backend uses Cloud Spanner to store user state. An overnight job exports user state to a Cloud Storage bucket. Your operations team needs __access to monitor__ the spanner instance but __not have the permissions to view or edit user data__. What IAM role should you grant the operations team?__[REVISAR]__

    * A. Grant the operations team roles/stackdriver.accounts. viewer IAM role.
    * B. Grant the operations team roles/spanner.database.reader IAM role.
    * C. **Grant the operations team roles/monitoring.viewer IAM role.**
    * D. Grant the operations team roles/spanner.database.user IAM role.

2. Your company has an App Engine application that needs to store stateful data in a proper storage service. Your data is non-relational data. You do not expect the database size to grow beyond 10 GB and you need to have the ability to scale down to zero to avoid unnecessary costs. Which storage service should you use?

    * A. Cloud SQL
    * B. Cloud Bigtable
    * C. **Cloud Datastore**
    * D. Cloud Dataproc

20. A mission-critical application running in Google Cloud Platform requires an urgent update to fix a security issue without any downtime. How should you do this in CLI using deployment manager?

    * A. Use gcloud deployment-manager resources create and point to the deployment config file.
    * B. Use gcloud deployment-manager resources update and point to the deployment config file.
    * **C. Use gcloud deployment-manager deployments update and point to the deployment config file.**
    * D. Use gcloud deployment-manager deployments create and point to the deployment config file.

22. An intern joined your team recently and needs access to Google Compute Engine in your sandbox project to explore various settings and spin up compute instances to test features. You have been asked to facilitate this. How should you give your intern access to compute engine without giving more permissions than is necessary?

    * A. Create a shared VPC to enable the intern access Compute resources.
    * B. Grant Project Editor IAM role for sandbox project.
    * C. **Grant Compute Engine Instance Admin Role for the sandbox project.**
    * D. Grant Compute Engine Admin Role for sandbox project.

23. A recent reorganization in your company has seen the creation of a new data custodian team– responsible for managing data in all storage locations. Your production GCP project uses buckets in Cloud Storage, and you need to delegate control to the new team to manage objects and buckets in your GCP project. What role should you grant them?

    * A. Grant the data custodian team Project Editor IAM role.
    * B. Grant the data custodian team Storage Object Creator IAM role.
    * **C. Grant the data custodian team Storage Admin IAM role.**
    * D. Grant the data custodian team Storage Object Admin IAM role.

24. You are the operations manager at your company, and you have been requested to provide administrative access to the virtual machines in the development GCP project to all members of the development team. There are over a hundred VM instances, and everyone at your company has a Google account. How can you simplify this access request while ensuring you can audit logins if needed?__[REVISAR]__

    * A. Run a script to generate SSH key pairs for all developers. Send an email to each developer with their private key attached. Add public keys to project-wide public SSH keysin your GCP project and configure all VM instances in the project to allow project-wide SSHkeys.
    * B. **Share a script with the developers and ask them to run it to generate a new SSH key pair.Have the developers add their public key to their Google Account. Ask the security administrator to grant    compute.osAdminLogin role to the developers’ Google group.**
    * C. Run a script to generate SSH key pairs for all developers. Send an email to each developer with their private key attached. Update all VM instances in the development to add all the public keys. Have the developers present their private key to SSH to the instances.
    * D. Share a script with the developers and ask them to run it to generate a new SSH key pair.Have them email their pubic key to you and run a script to add all the public keys to all instances in the project.

25. Your company owns a web application that lets users post travel stories. You began noticing errors in logs for a specific Deployment. The deployment is responsible for translating a post from one language to another. You’ve narrowed the issue down to a specific container named“msg-translator-22” that is throwing the errors. You are unable to reproduce the error in anyother environment, and none of the other containers serving the deployment have this issue. You would like to connect to this container to figure out the root cause. What steps would allow you to run commands against the msg-translator-22?

    * A. Use the kubectl run msg-translator-22 /bin/ bash command to run a shell on thatcontainer.
    * B. **Use the kubectl exec -it msg-translator-22 — /bin/bash command to run a shell on that container.**
    * C. Use the kubectl run command to run a shell on that container.
    * D. Use the kubectl exec Fit — /bin/bash command to run a shell on that container.

26. You want to list all the internal and external IP addresses of all __compute instances__. Which of the commands below should you run to retrieve this information?__[REVISAR]__

    * A. **gcloud compute instances list.**
    * B. gcloud compute networks list.
    * C. gcloud compute networks list-ip.
    * D. gcloud compute instances list-ip.

28. You are designing an application that lets users upload and share photos. You expect your application to grow really fast and you are targeting a worldwide audience. You want to delete uploaded photos after 30 days. You want to minimize costs while ensuring your application ishighly available. Which GCP storage solution should you choose?

    * A. Persistent SSD on VM instances.
    * B. Cloud Filestore.
    * C. **Multiregional Cloud Storage bucket.**
    * D. Cloud Datastore database.

29. You have a web application deployed as a managed instance group. You noticed some of the compute instances are running low on memory. You suspect this is due to JVM memory leak and you want to restart the compute instances to reclaim the leaked memory. Your web application is
currently serving live web trafic. You want to ensure that the available capacity does not go below 80% at any time during the restarts and you want to do this at the earliest. What would you do?__[REVISAR]__

   * A. Perform a rolling-action reboot with max-surge set to 20%.
   * B. **Perform a rolling-action restart with max-unavailable set to 20%.**
   * C. Stop instances in the managed instance group (MIG) one at a time and rely on autohealing to bring them back up.
   * D. Perform a rolling-action replace with max-unavailable set to 20%.

3. You are migrating a Python application from your on-premises data centre to Google Cloud.You want to deploy the application Google App Engine, and you modified the python application to use Cloud Pub/Sub instead of RabbitMQ. The application uses a specific service account which has the necessary permissions to publish and subscribe on Cloud Pub/Sub; however, the operations team __have not enabled the Cloud Pub/Sub API yet__. What should you do?__[REVISAR]__

    * A. Grant roles/pubsub.admin IAM role to the service account and modify the application code to enable the API before publishing or subscribing.
    * B. Configure the App Engine Application in GCP Console to use the specific Service Account with the necessary IAM permissions and rely on the automatic enablement of the Cloud Pub/Sub API on the fifist request to publish or subscribe.
    * C. **Navigate to the APIs & Services section in GCP console and enable Cloud Pub/Sub API.**
    * D. Use deployment manager to configure the App Engine Application to use the specific Service Account with the necessary IAM permissions and rely on the automatic enablement of the Cloud Pub/Sub API on the first request to publish or subscribe.

30. You created a Kubernetes deployment by running kubectl run nginx -image=nginx labels=“app=prod”. Your Kubernetes cluster is also used by a number of other deployments. How can you find the identifier of the pods for this nginx deployment?

    * A. kubectl get deployments –-output=pods
    * B. gcloud get pods –-selector=”app=prod”
    * C. **kubectl get pods -I “app=prod”**
    * D. gcloud list gke-deployments -filter={pod }

31. You developed an application that lets users upload statistical files and subsequently run analytics on this data. You chose to use Google Cloud Storage and BigQuery respectively for these requirements as they are highly available and scalable. You have a docker image for your
application code, and you plan to deploy on your on-premises Kubernetes clusters. Your on-prem Kubernetes cluster needs to connect to Google Cloud Storage and BigQuery and you want to do this in a secure way following Google recommended practices. What should you do?

   * A. Create a new service account, with editor permissions, generate and download a key.Use the key to authenticate inside the application.
   * B. **Create a new service account, grant it the least viable privileges to the required services,generate and download a JSON key. Use the JSON key to authenticate inside the application.**
   * C. Use the default service account for App Engine, which already has the required permissions.
   * D. Use the default service account for Compute Engine, which already has the required permissions.

32. Your company has deployed several production applications across many Google Cloud Projects. Your operations team requires a consolidated monitoring dashboard for all the projects. What should you do?

    * A. Set up a shared VPC across all production GCP projects and configure Cloud Monitoring dashboard on one of the projects.
    * B. Create a Stackdriver account in each project and configure all accounts to use the same service account. Create a monitoring dashboard in one of the projects.
    * C. **Create a single Stackdriver account and link all production GCP projects to it. Configure a monitoring dashboard in the Stackdriver account.**
    * D. Create a Stackdriver account and a Stackdriver group in one of the production GCP projects. Add all other projects as members of the group. Configure a monitoring dashboard in the Stackdriver account.

33. An engineer from your team accidentally deployed several new versions of NodeJS application on Google App Engine Standard. You are concerned the new versions are serving traffic. You have been asked to produce a list of all the versions of the application that are receiving trafic as well the percent trafic split between them. What should you do?

    * A. **gcloud app versions list --hide-no-traffic**
        > __--hide-no-traffic__ Only show versions that are receiving traffic.
    * B. gcloud app versions list --show-trafic
    * C. gcloud app versions list *-trafic
    * D. gcloud app versions list

35. You work for a big multinational financial company that has several hundreds of Google Cloud Projects for various development, test and production workloads. Financial regulations require your company to store all audit files for three years. What should you do to implement a log retention solution while minimizing storage cost?__[REVISAR]__

    * A. Export audit logs from Cloud Logging to Cloud Pub/Sub via an export sink. Configure a Cloud Dataflow pipeline to process these messages and store them in Cloud SQL for MySQL.
    * B. Write a script that exports audit logs from Cloud Logging to BigQuery. Use Cloud Scheduler to trigger the script every hour.
    * C. **Export audit logs from Cloud Logging to Coldline Storage bucket via an export sink.**
    * D. Export audit logs from Cloud Logging to BigQuery via an export sink.

36. Your company has three GCP projects – for development, test and production environments.The budgeting team in the finance department needs to know the cost estimates for the next financial year to include it in the budget. They have years of experience using SQL and need to group costs by parameters such as duration (day/week/month/quarter), service type, region, etc.How can you enable this?

    * A. Export billing data to a Google Cloud Storage bucket. Manually copy the data from Cloud Storage bucket to a Google sheet. Ask the budgeting team to apply formulas in the Google sheet to analyze current costs and estimate future costs.
    * B. **Export billing data to a BigQuery dataset. Ask the budgeting team to run queries against BigQuery to analyze current costs and estimate future costs.**
    * C. Download the costs as CSV file from the Cost Table page. Ask the budgeting team to open this file Microsoft Excel and apply formulas to analyze current costs and estimate future costs. 
    * D. Export billing data to a Google Cloud Storage bucket. Trigger a Cloud Function that reads the data and inserts into Cloud BigTable. Ask the budgeting team to run queries against BigTable to analyze current costs and estimate future costs.

37. You have files in a Cloud Storage bucket that you need to share with your suppliers. You want to restrict the time that the files are available to your suppliers to 1 hour. You want to follow Google recommended practices. What should you do?

    * A. Create a service account with just the permissions to access files in the bucket. Create a JSON key for the service account. Execute the command gsutil signurl -m 1h gs:///*.
    * B. **Create a service account with just the permissions to access files in the bucket. Create a JSON key for the service account. Execute the command gsutil signurl -d 1h gs:///++.**
    * C. Create a service account with just the permissions to access files in the bucket. Create a JSON key for the service account. Execute the command gsutil signurl -p 60m gs:///.
    * D. Create a JSON key for the Default Compute Engine Service Account. Execute the command gsutil signurl -t 60m gs:///***

38. You want to find a list of regions and the prebuilt images ofered by Google Compute Engine.Which commands should you execute to retrieve this information?

    * A. gcloud compute regions list, gcloud images list
    * B. **gcloud compute regions list, gcloud compute images list**
    * C. gcloud regions list, gcloud images list
    * D. gcloud regions list, gcloud compute images list

39. Your company produces documentary videos for a reputed television channel and stores its videos in Google Cloud Storage for long term archival. Videos older than 90 days are accessed only in exceptional circumstances and videos older than one year are no longer needed. How should you optimise the storage to reduce costs?__[REVISAR]__

    * A. Use a Cloud Function to rewrite the storage class to Coldline for objects older than 90 days. Use another Cloud Function to delete objects older than 365 days from Coldline Storage Class.
    * B. Use a Cloud Function to rewrite the storage class to Coldline for objects older than 90 days. Use another Cloud Function to delete objects older than 275 days from Coldline Storage Class.
    * C. Configure a lifecycle rule to transition objects older than 90 days to Coldline Storage Class. Configure another lifecycle rule to delete objects older than 275 days from Coldline Storage Class.
    * D. **Configure a lifecycle rule to transition objects older than 90 days to Coldline Storage Class. Configure another lifecycle rule to delete objects older than 365 days from Coldline Storage Class.**

4. You want to use Google Cloud Storage to host a static website on www.example.com for your staff. You created a bucket example-static-website and uploaded index.html and CSS files to it.You turned on static website hosting on the bucket and set up a CNAME record on www.example.com to point to :.storage.googleapis.com. You access the static website by navigating to www.example.com in the browser but your index page is not displayed. What should you do?__[REVISAR]__

    * A. Reload the Cloud Storage static website server to load the objects.
    * B. In example.com zone, modify the CNAME record to storage.googleapis.com/example-static-website
    * C. **Delete the existing bucket, create a new bucket with the name www.example.com and upload the html/css files.**
    * D. In example.com zone, delete the existing CNAME record and set up an A record instead to point to c.storage.googleapis.com.

40. You developed an enhancement to a production application deployed in App Engine Standard service. Unit testing and user acceptance testing has succeeded, and you deployed the new version to production. Users have started complaining of slow performance after the recent update, and you need to revert to the previous version immediately. How can you do this?__[REVISAR]__

    * A. Deploy the previous version as a new App Engine Application and use traffic splitting feature to send all trafiic to the new application.
    * B. In the App Engine Console, identify the App Engine application and select Revert.
    * C. **In the App Engine Console, identify the App Engine application versions and make the previous version the default to route all traffic to it.**
    * D. Execute gcloud app restore to rollback to the previous version.

41. You deployed a java application in a single Google Cloud Compute Engine VM. During peak usage, the application CPU is maxed out and results in stuck threads which ultimately make the system unresponsive, and requires a reboot. Your operations team want to receive an email alert when the CPU utilization is greater than 95% for more than 10 minutes so they can manually change the instance type to another instance that offers more CPU. What should you do?

    * A. **Link the GCP project to a Cloud Monitoring workspace. Configure an Alerting policy based on CPU utilization in Cloud Monitoring and trigger an email notification when the utilization exceeds the threshold.**
    * B. Write a custom script to monitor CPU usage and send an email notification when the usage exceeds the threshold.
    * C. In Cloud Logging, create logs based metric for CPU usage and store it as a custom metric in Cloud Monitoring. Create an Alerting policy based on CPU utilization in Cloud Monitoring and trigger an email notification when the utilization exceeds the threshold.
    * D. Link the project to a Cloud Monitoring workspace. Write a custom script that captures CPU utilization every minute and sends to Cloud Monitoring as a custom metric. Add an uptime check based on the CPU utilization.

42. You plan to deploy an application on an autoscaled managed instances group. The application uses a tomcat server and runs on port 8080. You want to access the application on https://www.example.com. You want to follow Google recommended practices. What services would you use?

    * A. Google DNS, Google CDN, SSL Proxy Load Balancer
    * B. Google Domains, Cloud DNS private zone, SSL Proxy Load Balancer
    * C. Google Domains, Cloud DNS private zone, HTTP(S) Load Balancer
    * D. **Google Domains, Cloud DNS, HTTP(S) Load Balancer**

43. You are hosting a new application on https://www.my-new-gcp-ace-website.com The static content of the application is served from /static path and is hosted in a Cloud Storage bucket. The dynamic content is served from/dynamic path and is hosted on a feet of compute engine instances be longing to a Managed Instance Group. How can you configure a single GCP LoadBalancer to serve content from both paths?__[REVISAR]__

    * A. Use HA Proxy Alpine Docker images to deploy to GKE cluster. Configure HA Proxy to route/dynamic/ to the Managed Instance Group (MIG) and/static/to GCS bucket. Create a service of type LoadBalancer. Create a DNS A record on www.my-new-gcp-ace-website.com to point to the address of LoadBalancer.
    * B. **Configure an HTTP(s) Load Balancer and configure it to route requests on /dynamic/to the Managed Instance Group (MIG) and /static/to GCS bucket. Create a DNS A record onwww.my-new-gcp-ace-website.com to point to the address of LoadBalancer.**
    * C. Configure an HTTP(s) Load Balancer for the Managed Instance Group (MIG). Configure the necessary TXT DNS records on www.my-new-gcp-ace-website.com to route requests on/dynamic/ to the Managed Instance Group (MIG) and /static/to GCS bucket.
    * D. Create a CNAME DNS record on www.my-new-gcp-ace-website.com to point to storage.googleapis.com. Configure an HTTP(s) Load Balancer for the Managed Instance Group (MIG). Set up redirection rules in Cloud Storage bucket to forward requests for non-static content to the Load Balancer address.

44. Your company recently migrated all infrastructure to Google Cloud Platform (GCP) and you want to use Google Cloud Build to build all container images. 
You want to store the build logs in Google Cloud Storage. 
You also have a requirement to push the images to Google Container Registry. 
You wrote a cloud build YAML con􀃕guration file with the following contents.
```yaml
steps:
    - name: gcr.io/cloud-builders/docker
    args: ('build', -t','gcr.io/[PROJECT_ID]/[IMAGE_NAME]'
    images: ['gcr.io/[PROJECT_ID]/[IMAGE_NAME]']
```
How should you execute Cloud build to satisfy these requirements?__[REVISAR]__

   * A. Execute gcloud builds run –config=[CONFIG_FILE_PATH]- –gcs-log-dir=[GCS_LOG_DIR][SOURCE]
   * B. Execute gcloud builds push –config=[CONFIG_FILE_PATH] [SOURCE]
   * C. Execute gcloud builds submit –config=[CONFIG_FILE_PATH] [SOURCE]
   * D. **Execute gcloud builds submit –config=[CONFIG_FILE_PATH]–gcs- –log-dir=[GCS_LOG_DIR][SOURCE]**

45. Your operations team have deployed an update to a production application running in Google Cloud App Engine Standard service. The deployment was successful, but your operations are unable to find this deployment in the production GCP project. What should you do?

    * A. Review the project settings in the App Engine application configuration files.
    * B. **Review the properties of the active gcloud configurations by executing gcloud config list.**
    * C. Review the project settings in the App Engine deployment YAML 􀃕le.
    * D. Review the project settings in the Deployment Manager console.

46. You have a Cloud Function that is triggered every night by Cloud Scheduler. The Cloud Function creates a snapshot of VMs running in all projects in the department. Your team created a new project ptech-vm, and you now need to provide IAM access to the service account used by the Cloud Function to let it create snapshots of VMs in the new ptech-vm project. You want to follow Google recommended practices. What should you do?__[REVISAR]__

    * A. **Grant Compute Storage Admin IAM role on the ptech-vm project to the service account used by the Cloud Function.**
    * B. Use gcloud to generate a JSON key for the existing service account used by the Cloud Function. Add a metadata tag to all compute engine instances in the ptech-vm project withkey: service-account and value: .
    * C. Set the scope of the service account to Read/Write when provisioning compute engine instances in the ptech-vm project.
    * D. Use gcloud to generate a JSON key for the existing service account used by the Cloud Function. Register the JSON key as SSH key on all VM instances in the ptech-vm project.

47. Your company has multiple GCP projects in several regions, and your operations team have created numerous gcloud configurations for most common operational needs. They have asked your help to retrieve an inactive gcloud configuration and the GKE clusters that use it, using the least number of steps. What command should you execute to retrieve this information?__[REVISAR]__

    * A. Execute gcloud config configurations describe.
    * B. Execute gcloud config configurations activate, then gcloud config list.
    * C. Execute kubectl config use-context, then kubectl config view.
    * D. **Execute kubectl config get-contexts.**

48. Your team uses Splunk for centralized logging and you have a number of reports and dashboards based on the logs in Splunk. You want to install Splunk forwarder on all nodes of your new Kubernetes Engine Autoscaled Cluster. The Splunk forwarder forwards the logs to a centralized Splunk Server. You want to minimize operational overhead. What is the best way to install Splunk Forwarder on all nodes in the cluster?

    * A. SSH to each node and run a script to install the forwarder agent.
    * B. **Include the forwarder agent in a DaemonSet deployment.**
    * C. Use Deployment Manager to orchestrate the deployment of forwarder agents on allnodes.
    * D. Include the forwarder agent in a StatefulSet deployment.

49. You work for a leading retail platform that enables its retailers to sell their items to over 200million users worldwide. You persist all analytics data captured during user navigation to BigQuery. A business analyst wants to run a query to identify products that were popular with buyers in the recent thanks giving sale. The analyst understands the query needs to iterate through billions of rows to fetch the required information but is not sure of the costs involved in the on-demand pricing model, and has asked you to help estimate the query cost. What should you do?

    * A. **Run the query using bq with the –dry_run flag to estimate the number of bytes read by the query. Make use of the pricing calculator to estimate the query cost.**
    * B. Run the query using bq with the –dry_run flag to estimate the number of bytes returned by the query. Make use of the pricing calculator to estimate the query cost.
    * C. Execute the query using bq to estimate the number of rows returned by the query. Make use of the pricing calculator to estimate the query cost.
    * D. Switch to BigQuery flat-rate pricing. Coordinate with the analyst to run the query while on flat-rate pricing and switch back to on-demand pricing.

5. Your company has many Citrix services deployed in the on-premises datacenter, and they all connect to the Citrix Licensing Server on 10.10.10.10 in the same data centre. Your company wants to migrate the Citrix Licensing Server and all Citrix services to Google Cloud Platform. You
want to minimize changes while ensuring the services can continue to connect to the Citrix licensing server. How should you do this in Google Cloud?__[REVISAR]__

   * A. Use gcloud compute addresses create to reserve 10.10.10.10 as a static external IP and assign it to the Citrix Licensing Server VM Instance.
   * B. Deploy the Citrix Licensing Server on a Google Compute Engine instance and set its ephemeral IP address to 10.10.10.10.
   * C. Deploy the Citrix Licensing Server on a Google Compute Engine instance with an ephemeral IP address. Once the server is responding to requests, promote the ephemeral IP address to a static internal IP address.
   * D. **Use gcloud compute addresses create to reserve 10.10.10.10 as a static internal IP and assign it to the Citrix Licensing Server VM Instance.**

50. Your company hosts a number of applications in Google Cloud and requires that log messages from all applications be archived for 10 years to comply with local regulatory requirements. Which approach should you use?

    * A. Grant the security team access to the logs in each Project
    * B. 1. Enable Stackdriver Logging API, 2. Configure web applications to send logs to Stackdriver, 3. Export logs to BigQuery
    * C. **1. Enable Stackdriver Logging API, 2. Configure web applications to send logs to Stackdriver, 3. Export logs to Google Cloud Storage**
    * D. 1. Enable Stackdriver Logging API, 2. Configure web applications to send logs to Stackdriver

6. You want to deploy a python application to an autoscaled managed instance group on Compute Engine. You want to use GCP deployment manager to do this. What is the fastest way to get the application on to the instances without introducing undue complexity?

    * A. Include a startup script to bootstrap the python application when creating an instance template by running gcloud compute instance-templates create app-template --startup-script=/scripts/install_app.sh
    * B. **Include a startup script to bootstrap the python application when creating an instance template by running gcloud compute instance-templates create app-template ––metadata-from-file startup-script=/scripts/install_app.sh**
    * C. Once the instance starts up, connect over SSH and install the application.
    * D. Include a startup script to bootstrap the python application when creating an instance template by running gcloud compute instance-templates create app-template –-metadata-from-file startup-script-url=/scripts/install_app.sh

7. You deployed your application to a default node pool on the GKE cluster and you want to configure cluster autoscaling for this GKE cluster. For your application to be proftable, you must limit the number of Kubernetes nodes to 10. You want to start small and scale up as traffic increases and scale down when the traffic goes down. What should you do?

    * A. **Update existing GKE cluster to enable autoscaling by running the command gcloud container clusters update [CLUSTER_NAME] enable-autoscaling --min-nodes=1 –-max-nodes=10**
    * B. Set up a stack driver alert to detect slowness in the application. When the alert is triggered, increase nodes in the cluster by running the command gcloud container clusters resize CLUSTER_Name -size .
    * C. Create a new GKE cluster by running the command gcloud container clusters create[CLUSTER_NAME] -–enable-autoscaling -–min-nodes=1 --max-nodes=10.
    * D. Redeploy your application To enable autoscaling, add a tag to the instances in the cluster by running the command gcloud compute instances add-tags [INSTANCE] --tags=enable-autoscaling,min-nodes=1,max-nodes=1

8. Your company plans to store sensitive PII data in a cloud storage bucket. Your compliance department has asked you to ensure the objects in this bucket are encrypted by customer-managed encryption keys. What should you do?__[REVISAR]__

    * A. In the bucket advanced settings, select Customer-supplied key and then select a Cloud KMS encryption key.
    * B. **In the bucket advanced settings, select Customer-managed key and then select a Cloud KMS encryption key.**
    * C. Recreate the bucket to use a Customer-managed key. Encryption can only be specificed at the time of bucket creation.
    * D. In the bucket advanced settings, select Google-managed key and then select a Cloud KMS encryption key.

9. You have developed an enhancement for a photo compression application running on the App Engine Standard service in Google Cloud Platform, and you want to canary test this enhancement on a small percentage of live users. How can you do this?

    * A. Deploy the enhancement as a new App Engine Application in the existing GCP project. Make use of App Engine native routing to have the old App Engine application proxy 1% of the requests to the new App Engine application.
    * B. **Use gcloud app deploy to deploy the enhancement as a new version in the existing application and use –splits flag to split the traffic between the old version and the new version. Assign a weight of 1 to the new version and 99 to the old version.**
    * C. Use gcloud app deploy to deploy the enhancement as a new version in the existing application with -migrate flag.
    * D. Deploy the enhancement as a new App Engine Application in the existing GCP project.Configure the network load balancer to route 99% of the requests to the old (existing) App Engine Application and 1% to the new App Engine Application.

BUENAS  . 30
MALAS . 20