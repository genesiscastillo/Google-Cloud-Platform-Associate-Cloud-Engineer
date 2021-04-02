# Google Associate Cloud Engineer Practice 
# Exam Part - 4

1. You developed an application that reads objects from a cloud storage bucket. You followed GCP documentation and created a service account with just the permissions to read objects from the cloud storage bucket. However, when your application uses this service account, it fails to read objects from the bucket. You suspect this might be an issue with the permissions assigned to the service account. You would like to authenticate a gsutil session with the service account credentials, reproduce the issue yourself and identify the root cause. How can you authenticate gsutil with service account credentials?

    * A. Create JSON keys for the service account and execute gcloud authenticate service-account –-key-file [KEY_FILE].
    * B. Create JSON keys for the service account and execute gcloud authenticate activate-service-account –-key-file [KEY_FILE].
    * C. **Create JSON keys for the service account and execute gcloud auth activate-service-account -–key-file [KEY_FILE].**
    * D. Create JSON keys for the service account and execute gcloud auth service-account –-key-file [KEY_FILE].

10. You have an application deployed in a GKE Cluster as a Kubernetes workload with DaemonSets. Your application has become very popular and is now struggling to cope up with increased trafic. You want to add more pods to your workload and want to ensure your cluster scales upand scales down automatically based on volume. What should you do?

    * A. Enable autoscaling on Kubernetes Engine.
    * B. Perform a rolling update to modify machine type from 11-standard-2 to n1- – standard-4.
    * C. **Enable Horizontal Pod Autoscaling for the Kubernetes deployment.**
    * D. Create another identical Kubernetes workload and split trafic between the two workloads.

11. You developed an application to serve production users and you plan to use Cloud SQL to host user state data which is very critical for the application flow. You want to protect your user state data from zone failures. What should you do?

    * A. Create a Read replica in the same region but in a diferent zone.
    * B. Configure High Availability (HA) for Cloud SQL and Create a Failover replica in the same region but in a diferent zone.
    * C. Create a Read replica in a diferent region.
    * D. **Configure High Availability (HA) for Cloud SQL and Create a Failover replica in a diferent region.**

12. Your Company is planning to migrate all Java web applications to Google App Engine. However, you still want to continue using your on-premise database. How can you set up the appengine to communicate with your on-premise database while minimizing effort?

    * A. Setup the application using App Engine Flexible environment with Cloud Router to connect to an on-premise database.
    * B. Setup the application using App Engine Standard environment with Cloud VPN to connect to an on-premise database.
    * C. Setup the application using App Engine Standard environment with Cloud Router toc onnect to an on-premise database.
    * D. **Setup the application using App Engine Flexible environment with Cloud VPN to connect to an on-premise database.**

13. You want to migrate an XML parser application from the on-premises data centre to GoogleCloud Platform. You created a development project, set up the necessary IAM roles and deployed the application in a compute engine instance. The testing has succeeded, and you are ready to deploy the staging instance. You want to create the same IAM roles in a new staging GCP project.How can you do this eficiently without compromising security?

    * A. Make use of gcloud iam roles copy command to copy the IAM roles from the Development GCP organization to the Staging GCP organization.
    * B. Make use of Create Role feature in GCP console to create all necessary IAM roles from new in the Staging project.
    * C. **Make use of gcloud iam roles copy command to copy the IAM roles from the Development GCP project to the Staging GCP project.**
    * D. Make use of the Create Role from Role feature in GCP console to create IAM roles in the Staging project from the Development IAM roles.

14. Your company’s auditors carry out an annual audit every year and have asked you to provide them with all the IAM policy changes in Google Cloud since the last audit. You want to streamline and expedite the analysis for audit. How should you share the information requested by auditors?

    * A. Export all audit logs to Cloud Pub/Sub via an export sink. Use a Cloud Function to read the messages and store them in Cloud SQL. Make use of ACLs and views to restrict the data shared with the auditors.
    * B. **Export all audit logs to Google Cloud Storage bucket and set up the necessary IAM acces to restrict the data shared with auditors.**
    * C. Export all audit logs to BigQuery dataset. Make use of ACLs and views to restrict the data shared with the auditors.
    * D. Have the auditors query the required information quickly. Configure alerts in Cloud Monitoring and trigger notifications to the auditors.

15. You work at a large organization where each team has a distinct role. The development team can create Google Cloud projects but can’t link them to a billing account – this role is reserved for the finance team, and the development team do not want finance team to make changes to their project resources. How should you configure IAM access controls to enable this?

    * A. **Grant the development team Billing Account User (roles/billing.user) role on the billing account and Project Billing Manager (roles/billing.projectManager) on the GCP organization.**
    * B. Grant the finance team Billing Account User (roles/billing.user) role on the billing account and Project Billing Manager roles/billing.projectManager) on the GCP organization.
    * C. Grant the finance team Billing Account User (roles/billing.user) role on the billing account.
    * D. Grant the development team Billing Account User (roles/billing.user) role on the billing account.

16. You have a number of applications that have bursty workloads and are heavily dependent on topics to decouple publishing systems from consuming systems. Your company would like to go serverless to enable developers to focus on writing code without worrying about infrastructure. Your solution architect has already identified Cloud Pub/Sub as a suitable alternative for decoupling systems. You have been asked to identify a suitable GCP Serverless service that is easy to use with Cloud Pub/Sub. You want the ability to scale down to zero when there is no traffic in order to minimize costs. You want to follow Google recommended practices. Whatshould you suggest?

    * A. Cloud Run for Anthos
    * B. Cloud Run
    * C. App Engine Standard
    * D. **Cloud Functions.**

17. You deployed a Java application on four Google Cloud Compute Engine VMs in two zones behind a network load balancer. During peak usage, the application has stuck threads. This issue ultimately takes down the whole system and requires a reboot of all VMs. Your operations team have recently heard about self-healing mechanisms in Google Cloud and have asked you to identify if it is possible to automatically recreate the VMs if they remain unresponsive for attempts 10 seconds apart. What should you do?

    * A. Enable autoscaling on the Managed Instance Group (MIG).
    * B. Enable autohealing and set the autohealing health check to healthy (HTTP).
    * C. Use a global HTTP(s) Load Balancer instead and limit Requests Per Second (RPS) to 10.
    * D. Use a global HTTP(s) Load Balancer instead and set the load balancer health check tohealthy (HTTP).

18. You’ve created a Kubernetes engine cluster named “my-gcp-ace-proj-1”, which has a clusterpool named my-gcp-ace-primary-node-pool. You want to increase the number of nodes within your cluster pool from 10 to 20 to meet capacity demands. What is the command to change the number of nodes in your pool?

    * A. gcloud container clusters update my-gcp-ace-proj-1 – -node-pool my-gcp-ace- primary-node-pool -num-nodes 20
    * B. gcloud container clusters resize my-gcp-ace-proj- 1 – -node-pool my-gcp-ace- primary-node-pool -new-size 20
    * C. **gcloud container clusters resize my-gcp-ace-proj- 1 –-node-pool my-gcp-ace-primary-node-pool --num-nodes 20**
    * D. kubectl container clusters update my-gcp-ace-proj-1 – -node-pool my-gcp-ace- primary-node-pool–num-nodes 20

19. A company wants to build an application that stores images in a Cloud Storage bucket and wants to generate thumbnails as well as resize the images. They want to use a google managed service that can scale up and scale down to zero automatically with minimal efort. You have been asked to recommend a service. Which GCP service would you suggest?

    * A. Google Compute Engine
    * B. Google App Engine
    * C. **Cloud Functions**
    * D. Google Kubernetes Engine

2. Your company is migrating a mission-critical application from the on-premises data centre to Google Cloud Platform. The application requires 12 Compute Engine VMs to handle traffic at peak usage times. Your operations team have asked you to ensure the VMs restart automatically (i.e.without manual intervention) if/when they crash, and the processing capacity of the applicationdoes not reduce down during system maintenance. What should you do?

    * A. Deploy the application on a Managed Instance Group (MIG) that disables the creation retry mode by setting the -nocreation-retries flag.
    * B. Create an instance template with availability policy that turns of the automatic restart behaviour and sets on-host maintenance to terminate instances during maintenance events. Deploy the application on a Managed Instance Group (MIG) based on this template.
    * C. Deploy the application on a Managed Instance Group (MIG) with autohealing healthcheck set to healthy (HTTP).
    * D. **Create an instance template with availability policy that turns on the automatic restart behaviour and sets on-host maintenance to live migrate instances during maintenance events. Deploy the application on a Managed Instance Group (MIG) based on this template.**

20. You want to ensure the boot disk of a preemptible instance is persisted for re-use. How should you provision the gcloud compute instance to ensure your requirement is met.

    * A. gcloud compute instances create [INSTANCE_NAME] -preemptible. The flag — boot-disk-auto-delete is disabled by default.
    * B. gcloud compute instances create [INSTANCE_NAME] -preemptible — -boot-disk- auto-delete=no
    * C. **gcloud compute instances create [INSTANCE_NAME] -–preemptible -— no-boot-disk-auto-delete**
    * D. gcloud compute instances create [INSTANCE_NAME] -no-auto-delete

21. You want to ingest and analyze large volumes of stream data from sensors in real-time, matching the high speeds of loT data to track normal and abnormal behavior. You want to run it through a data processing pipeline and store the results. Finally, you want to enable customers to build dashboards and drive analytics on their data in real-time. What services should you use forthis task?

    * A. Cloud Pub/Sub, Cloud Dataflow, Cloud Dataprep
    * B. Stackdriver, Cloud Dataflow, BigQuery
    * C. Cloud Pub/Sub, Cloud Dataflow, Cloud Dataproc
    * D. **Cloud Pub/Sub, Cloud Dataflow, BigQuery**

22. Your company is migrating an application from its on-premises data centre to Google Cloud. One of the applications uses a custom Linux distribution that is not available on Google Cloud. Your solution architect has suggested using VM Ware tools to exporting the image and store it in a Cloud Storage bucket. The VM Image is a single compressed 64 GB tar file. You started copying this file using gsutil over a dedicated 1Gbps network, but the transfer is taking a very long time to complete. Your solution architect has suggested using all of the 1Gbps Network to transfer the file quickly. What should you do?

    * A. Use parallel composite uploads to speed up the transfer.
    * B. Upload the file Multi-Regional instead and move the file to Nearline Storage Class.
    * C. Restart the transfer from GCP console.
    * D. Increase the transfer speed by decreasing the TCP window size.

23. You want to migrate an application from Google App Engine Standard to Google App Engine Flex. Your application is currently serving live traffic and you want to ensure everything is working in Google App Engine Flex before migrating all traffic. You want to minimize effort and ensure the availability of service. What should you do?

    * A. 1. Set env: app-engine-flex in app.yaml 2. gcloud app deploy -no-promote -version=[NEW_VERSION] 3. Validate [NEW_VERSION] in App Engine Flex 4. gcloud app versions start[NEW_VERSION]
    * B. 1. Set env: app-engine-flex in app.yaml 2. gcloud app deploy –version=[NEW_VERSION] 3.Validate [NEW_VERSION] in App Engine Flex 4. gcloud app versions start [NEW_VERSION]
    * C. Set env: flex in app.yaml 2. gcloud app deploy–no-promote –version=[NEW_VERSION] 3.Validate [NEW_VERSION] in App Engine Flex 4. gcloud app versions migrate [NEW_VERSION]
    * D. **Set env: flex in app.yaml 2. gcloud app deploy –version=[NEW_VERSION] 3. Validate[NEW_VERSION] in App Engine Flex 4. gcloud app versions migrate [NEW_VERSION]**

24. Your company collects and stores CCTV footage videos in raw format in Google Cloud Storage. Within the first 30 days, the footage is processed regularly for detecting patterns such asthreat/object/face detection and suspicious behavior detection. You want to minimize the cost of storing all the data in Google Cloud. How should you store the videos?

    * A. Use Google Cloud Regional Storage for the first 30 days, and use lifecycle rules to transition to Nearline Storage.
    * B. **Use Google Cloud Nearline Storage for the first 30 days, and use lifecycle rules to transition to Coldline Storage**.
    * C. Use Google Cloud Regional Storage for the first 30 days, and then move videos to Google Persistent Disk.
    * D. **Use Google Cloud Regional Storage for the first 30 days, and use lifecycle rules to transition to Coldline Storage.**

25. You migrated an internal HR system from an on-premises database to Google Cloud Compute Engine Managed Instance Group (MIG). The networks team at your company has asked you to associate the internal DNS records of the VMs with a custom DNS zone. You want to follow Google recommended practices. What should you do?

    * A. 1.Create a new Cloud DNS zone and a new VPC and associate the DNS zone with the VPC.2. When provisioning the VMs, associate the DNS records with the new DNS zone. 3.Configure firewall rules to block all external (public) trafic. 4. Finally, configure the DNS zone associated with the default VPC to direct all requests to the new DNS zone.
    * B. 1.Provision the VMs with custom hostnames.
    * C. 1.Create a new Cloud DNS zone and set its visibility to private. 2. When provisioning the VMs, associate the DNS records with the new DNS zone.
    * D. 1.Install a new BIND DNS server on Google Compute Engine, using the BIND name server software (BIND9). 2. Configure a Cloud DNS forwarding zone to direct all requests to the Internal BIND DNS server. 3. When provisioning the VMs, associate the DNS records withthe Internal BIND DNS server.

27. Your team is working towards using the desired state configuration for your application deployed on the GKE cluster. You have YAML files for the Kubernetes Deployment and Service objects. Your application is designed to have 2 pods, which is defined by the replicas parameter in app-deployment.yaml. Your service uses GKE Load Balancer which is defined in app-service.yaml. You created the Kubernetes resources by running (1) kubectl apply -f app-deployment.yaml (2) kubectl apply -f app-service.yaml. Your deployment is now serving live traffic but is sufering from performance issues. You want to increase the number of replicas to 5. What should you do in order to update the replicas in existing Kubernetes deployment objects?

    * A. Disregard the YAML 􀃕le. Enable autoscaling on the deployment to trigger on CPU usageand set max pods to 5. kubectl autoscale myapp—max=5–cpu- percent=80
    * B. Modify the current configuration of the deployment by using kubectl edit to open the YAML file of the current configuration, modify and save the configuration. kubectl edit deployment/app-deployment-o yaml –save-config
    * C. Disregard the YAML file. Use the kubectl scale command to scale the replicas to 5. kubectl scale -replicas= -f app-deployment.yaml
    * D. **Edit the number of replicas in the YAML file and rerun the kubectl apply. kubectl apply -f app-deployment.yaml**

28. An application that you are migrating to Google Cloud relies on overnight batch jobs that take between 2 to 3 hours to complete. You want to do this at a minimal cost. Where should you run these batch jobs?

    * A. Run the batch jobs in a non-preemptible shared core compute engine instance that supports short periods of bursting.
    * B. Run the batch jobs in a GKE cluster on a node pool with four instances of type f1-micro.
    * C. Run the batch jobs in a GKE cluster on a node pool with a single instance of type e2-small.
    * D. **Run the batch jobs in a preemptible compute engine instance of appropriate machine type.**

29. You created a Kubernetes deployment by running: kubectl run nginx –-image=nginx -replicas=1. After a few days, you decided you no longer want this deployment. You identifed the pod and deleted it by running kubectl delete pod. You noticed the pod got recreated.

    ```bash
    $ kubectl get pods 
    ```
    NAME| READY| STATUS| RESTARTS| AGE
    ---|---|---|---|--- 
    nginx-84748895c4-nqqmt1 1/1| Running |0| 9m41s
    ```bash
    $ kubectl delete pod nginx-84748895c4-nqqmt pod

    “nginx-84748895c4-nqqat” deleted 

    $ kubectl get pods 
    ```
    NAME| READY| STATUS| RESTARTS| AGE|
    ---|---|---|---|--- 
    nginx-84748895c4-k6bzl| 1/1| Running| 0| 25s
    
    What should you do to delete the deployment and avoid pod getting recreated?

    * A. **kubectl delete deployment nginx**
    * B. kubectl delete –deployment=nginx
    * C. kubectl delete pod nginx-84748895c4-k6bzl –no-restart 2
    * D. kubectl delete inginx

3. You are enhancing a production application currently running on an Ubuntu Linux VM on Google Compute Engine. The new enhancements require a connection to Cloud SQL to persist user addresses. Your colleague has created the Cloud SQL instance and an IAM service account with the correct permissions but doesn’t know how to configure the VM to use this serviceaccount, and has asked for your assistance. What should you do?

    * A. Execute gcloud iam service-accounts keys create to generate a ISON key for the serviceaccount. Add a metadata tag on the GCP project with key: service-account and value: .
    * B. Set the service account in the Identity and API access section when provisioning the compute engine VM.
    * C. **Execute gcloud iam service-accounts keys create to generate a JSON key for the serviceaccount. Add a metadata tag to the compute instance with key: service-account and value:**
    * D. Execute gcloud iam service-accounts keys create to generate a JSON key for the serviceaccount. Copy the contents of JSON key to ~/identity/default-service-account.json overwrite the default service account.

30. You created a cluster.YAML file containing : 
    resources: 
        – name: cluster 
          type: container.vl.cluster 
    properties: 
        zone: europe-west1-b 
        cluster: 2 
        description: “My GCP ACE cluster”
        initialNodeCount: 2 
    
    You want to use Cloud Deployment Manager to create this cluster in GKE.What should you do?

    * A. **gcloud deployment-manager deployments create my-gcp-ace-cluster –-config cluster.yaml**
    * B. gcloud deployment-manager deployments apply my-gcp-ace-cluster --type container.v1.cluster –-config cluster.yaml
    * C. gcloud deployment-manager deployments apply my-gcp-oce-cluster –-config cluster.yaml
    * D. gcloud deployment-manager deployments create my-gcp-ace-cluster –-type container.v1.cluster –-config cluster.yaml

31. Your company, which runs highly rated mobile games, has chosen to migrate its analytics backend to BigQuery. The analytics team of 7 analysts need access to perform queries against the data in BigQuery. The analytics team members change frequently. How should you grant them access?

    * A. Create a Cloud Identity account for each analyst and grant roles/bigquery.dataViewelrole to each account.
    * B. **Create a Cloud Identity account for each analyst and add them all to a group. Grant roles/bigquery.jobUser role to the group.**
    * C. Create a Cloud Identity account for each analyst and add them all to a group. Grant roles/bigquery.dataViewer role to the group.
    * D. Create a Cloud Identity account for each analyst and grant roles/bigquery.jobUser role to each account.

32. Your company plans to store sensitive PII data in a cloud storage bucket. Your compliance department doesn’t like encrypting sensitive PII data with Google-managed keys and has asked you to ensure the new objects uploaded to this bucket are encrypted by customer-managed encryption keys. What should you do?(Select Three)__[REVISAR]__

    * A. In the bucket advanced settings, select the Customer-supplied key and then select a Cloud KMS encryption key.
    * B. Use gsutil with –encryption-key=[ENCRYPTION_KEY] when uploading objects to the bucket.
    * C. In the bucket advanced settings, select the Customer-managed key and then select a Cloud KMS encryption key.
    * D. **Modify .boto configuration to include encryption_key = [KEY_RESOURCE] when uploading objects to bucket.**
    * E. **Use gsutil with -O “GSUtil:encryption_key=[KEY_RESOURCE]’ when uploading objects to the bucket.**

33. Your company recently acquired a startup that lets its developers pay for their projects using their company credit cards. You want to consolidate the billing of all GCP projects into a new billing account. You want to follow Google recommended practices. How should you do this?__[REVISAR]__

    * A. Send an email to billing.support@cloud.google.con and request them to create a new billing account and link all the projects to the billing account.
    * B. Raise a support request with Google Billing Support and request them to create a new billing account and link all the projects to the billing account.
    * C. In the GCP Console, move all projects to the root organization in the Resource Manager.
    * D. Ensure you have the Billing Account Creator Role. Create a new Billing account yourself and set up a payment method with company credit card details.

34. You are enhancing a production application currently running on an Ubuntu Linux VM on Google Compute Engine. The new enhancements require a connection to SQL Server instance to persist user appointments. Your colleague has provisioned an SQL Server instance in a Google Compute Engine VM in US-Central region and has asked for your assistance to RDP to the VM in the least number of steps. What should you suggest?

    * A. Add a firewall rule to allow TCP trafic on port 3389. In the GCP console, add a username and password for the Windows VM instance. Install Chrome RDP for Google Cloud Platform extension and click the RDP button in the console to connect to the instance with the credentials.  
    * B. In the GCP console, add a username and password for the Windows 0 VM instance.Install an RDP client and connect to the instance with username and password.
    * C. **Add a firewall rule to allow TCP trafic on port 3389. Install an RDP client and connect to the instance.**  
    * D. Add a firewall rule to allow TCP trafic on port 22. In the GCP console, add a password for the Windows VM instance. Install Chrome RDP for Google Cloud Platform extension and click the RDP button in the console to connect to the instance with the credentials.

36. You have two compute instances in the same VPC but in diferent regions. You can SSH from one instance to another instance using their external IP address but not their internal IP address.What could be the reason for SSH failing on the internal IP address?

    * A. The compute instances have a static IP for their internal IP.
    * B. **The combination of compute instance network tags and VPC firewall rules allow SSH from 0.0.0.0 but denies SSH from the VPC subnets IP range.**
    * C. The internal IP address is disabled.
    * D. The compute instances are not using the right cross-region SSH IAM permissions.

37. Your team is responsible for the migration of all legacy on-premises applications to GoogleCloud. Your team is a big admirer of serverless and has chosen App Engine Standard as the preferred choice for compute workloads. Your manager asked you to migrate a legacy accounting application built in C++, but you realized App Engine Standard doesn’t support C++. What GCP compute services should you use instead to maintain the serverless aspect?(Choose two answers)

    * A. **Deploy the containerized version of the application in Cloud Run.**
    * B. Deploy the containerized version of the application in Cloud Run on GKE.
    * C. **Deploy the containerized version of the application in Google Kubernetes Engine (GKE).**
    * D. Deploy the containerized version of the application in App Engine Flex.
    * E. Convert the application into a set of functions and deploy them in Google Cloud Functions.

38. Your company runs several internal applications on bare metal Kubernetes servers in your on-premises data centre. One of the applications deployed in the Kubernetes cluster uses a NASshare to save files. In preparation for the upcoming migration to Google Cloud, you want to update the application to use Google Cloud Storage instead; however, security policies prevent virtual machines from having public IP addresses. What should you do?

    * A. Configure a VPN tunnel between the on-premises data centre and the GCP VPC. Create a custom route in the VPC for Google Restricted APIs IP range (199.36.153.4/30) and propagate the route over VPN. Resolve *.googleapis.com as a CNAME record to restricted.googleapis.com in your on-premises DNS server.
    * B. Make an exception and assign public IP addresses to the servers. Configure firewall rules to allow trafic from the VM public IP addresses to the IP range of Cloud Storage.
    * C. Create a new VPC in GCP and deploy a proxy server like HAProxy/Squid to forward requests to Cloud Storage. Configure a VPN tunnel between the on- premises data centre and the GCP VPC. Have the servers access Cloud Storage through the proxy.
    * D. Migrate all VMs from the data centre to Google Compute Engine. Set up a Load Balancer on the GCP bucket and have the servers access Cloud Storage through the load balancer.

39. You want to persist logs for 10 years to comply with regulatory requirements. You want to follow Google recommended practices. Which Google Cloud Storage class should you use?

    * A. Coldline storage class
    * B. **Archive storage class**
    * C. Nearline storage class
    * D. Standard storage class

4. A GKE cluster (test environment) in your test GCP project is experiencing issues with a sidecar container connecting to Cloud SQL. This issue has resulted in a massive amount of log entries in Cloud Logging and shot up your bill by 25%. Your manager has asked you to disable these logs asquickly as possible and using the least number of steps. You want to follow Google recommended practices. What should you do?

    * A. In Cloud Logging, disable the log source for GKE Cluster Operations resource in the Logs ingestion window.
    * B. **Recreate the GKE cluster and disable Cloud Logging.**
        > __--enable-stackdriver-kubernetes__
Enable Cloud Operations for GKE. To enable only Cloud Monitoring use --enable-stackdriver-kubernetes and --no-enable-cloud-logging. To enable only Cloud Logging use --enable-stackdriver-kubernetes and --no-enable-cloud-monitoring.
    * C. Recreate the GKE cluster and disable Cloud Monitoring.
    * D. In Cloud Logging, disable the log source for GKE container resource in the Logs ingestion window.

40. You are in the process of migrating a mission-critical application from your on- premises datacentre to Google Kubernetes Engine (GKE). Your operations team do not want to take on the overhead for upgrading the GKE cluster and have asked you to ensure the Kubernetes version is always stable and supported. What should you do?

    * A. When provisioning the GKE cluster, ensure you use the latest stable and supported version.
    * B. Update your GKE cluster to turn on GKE’s node auto-upgrade feature.
    * C. When provisioning the GKE cluster, use Container Optimized os node images.
    * D. Update your GKE cluster to turn on GKE’s node auto-repair feature.

41. You have two workloads on GKE (Google Kubernetes Engine) – create-order and dispatch-order. create-order handles the creation of customer orders, and dispatch- order handles dispatching orders to your shipping partner. Both create-order and dispatch-order workloads have cluster autoscaling enabled. The create-order deployment needs to access (i.e. invoke webservice of) dispatch-order deployment. dispatch-order deployment cannot be exposed publicly.How should you define the services?

    * A. Create a Service of type ClusterlP for dispatch-order. Have create- order use the ServiceIP address.
    * B. Create a Service of type LoadBalancer for dispatch-order and an Ingress S Resource forthat Service. Have create-order use the Ingress IP address.
    * C. Create a Service of type LoadBalancer for dispatch-order. Have create-order use theService IP address.
    * D. **Create a Service of type NodePort for dispatch-order and an Ingress Resource for that Service. Have create-order use the Ingress IP address.**

42. Your company runs a very successful web platform and has accumulated 3 petabytes of customer activity data in sharded MySQL database located in your datacenter. Due to storage limitations in your on-premise data center, your company has decided to move this data to GCP.The data must be available all through the day. Your business analysts, who have experience ofusing a SQL Interface, have asked for a seamless transition. How should you store the data so that availability is ensured while optimizing the ease of analysis for the business analysts?

    * A. **Import data into Google BigQuery.**
    * B. Import flat files into Google Cloud Storage.
    * C. Import data into Google Cloud Datastore.
    * D. Import data into Google Cloud SQL

43. Your manager asked you to write a script to upload objects to a Cloud Storage bucket. How should you set up the IAM access to enable the script running in a Google Compute VM upload objects to Cloud Storage?

    * A. Create a new IAM service account with the access scope cloud-platform and configure the script to use this service account.
    * B. **Grant roles/storage.objectCreator IAM role to the service account used by the VM.**
    * C. Grant roles/storage.objectAdmin IAM role to the service account used by the VM.
    * D. Create a new IAM service account with the access scope devstorage.write_only and configure the script to use this service account

44. You are migrating your on-premises workloads to GCP VPC, and you want to use Compute Engine virtual machines. You want to separate the Finance team VMs and the Procurement team VMs into separate subnets. You need all VMs to communicate with each other over their internal IP addresses without adding routes. What should you do?

    * A. **Use Deployment Manager to create a new VPC with 2 subnets in 2 diferent regions. Ensure the subnets use non-overlapping IP range.**
    * B. Use Deployment Manager to create a new VPC with 2 subnets in the same region. Ensure the subnets use the same IP range.
    * C. Use Deployment Manager to create two VPCs, each with a subnet in a diferent region. Ensure the subnets use non-overlapping IP range.
    * D. Use Deployment Manager to create two VPCs, each with a subnet in the same 0 region. Ensure the subnets use overlapping IP range.

45. Your compliance team requested all audit logs are stored for 10 years and to allow access for external auditors to view. You want to follow Google recommended practices. What should youdo?(Choose two)

    * A. Create an account for auditors to have view access to Stackdriver Logging.
    * B. Export audit logs to Cloud Storage via an export sink.
    * C. Export audit logs to Splunk via a Pub/Sub export sink.
    * D. Generate a signed URL to the Stackdriver export destination for auditors to access.
    * E. **Export audit logs to BigQuery via an export sink.**

46. Your company plans to migrate all applications from its on-premises data centre to Google Cloud Platform. The DevOps team currently use Jenkins extensively to automate configuration updates in applications. How should you provision Jenkins in Google Cloud with the least number of steps?

    * A. Download Jenkins binary from https://www.jenkins.io/download/ and deploy in Google App Engine Standard Service.
    * B. Create a Kubernetes Deployment YAML file referencing the Jenkins docker image and deploy to a new GKE cluster.
    * C. Download Jenkins binary from https://www.jenkins.io/download/ and deploy in a new Google Compute Engine instance.
    * D. **Provision Jenkins from GCP marketplace.**

47. You have a number of compute instances be longing to an unmanaged instances group. You need to SSH to one of the Compute Engine instances to run an ad hoc script. You’ve already authenticated gcloud, however, you don’t have an SSH key deployed yet. In the fewest steps possible, what’s the easiest way to SSH to the instance?

    * A. Run gcloud compute instances list to get the IP address of the instance, then use the ssh command.
    * B. **Use the gcloud compute ssh command.**
    * C. Create a key with the ssh-keygen command. Then use the gcloud compute ssh command.
    * D. Create a key with the ssh-keygen command. Upload the key to the instance. Run gcloud compute instances list to get the IP address of the instance, then use the ssh command.

48. Your compliance department has asked you to share a compressed zip of sensitive audit logs with an external auditor. The external auditor does __not have a Google account__, and you want to remove the access after 4 hours. How can you do this securely with the least number of steps?

    * A. Configure Static Website hosting on the Cloud Storage bucket, make the zip file public and ask the auditor to download the file from the website.
    * B. Delete the zip file after 4 hours. Copy the zip file to a new Cloud Storage bucket, makethe bucket public and share the URL securely with the external auditor.
    * C. Delete the new bucket after 4 hours. Use gcloud to generate a signed URL on the object with a four-hour expiry. Securely share the URL with the external auditor.
    * D. **Make the zip file public and securely share the URL with the external auditor. Set up a lifecycle policy to delete the object after 4 hours.**

49. You have three gcloud configurations – one for each of development, test and production projects. You want to list all the configurations and switch to a new configuration. With the fewest steps possible, what’s the fastest way to switch to the correct configuration?

    * A. **To list configurations gcloud config configurations list To activate a configuration – gcloud config configurations activate.**
    * B. To list configurations gcloud config list To activate a configuration – gcloud config activate.
    * C. To list configurations – gcloud configurations list To activate a configuration gcloud config activate.
    * D. To list configurations – gcloud configurations list To activate a configuration gcloud configurations activate

50. You are exploring the possibility of migrating a mission-critical application from your on-premises data centre to Google Cloud Platform. You want to host this on a GKE cluster with autoscaling enabled, and you need to ensure each node can run a pod to push the application logs to a third-party logging platform. How should you deploy the pod?

    * A. **Initialize the logging pod during the GKE Cluster creation.**
    * B. Add the logging pod in the Deployment YAML file.
    * C. Deploy the logging pod in a DaemonSet Kubernetes object.
    * D. Deploy the logging pod in a StatefulSet Kubernetes object.

6. You are developing a simple application in App Engine Standard service. Unit testing and user acceptance testing has succeeded, and you want to build a new App Engine application to serve as your performance testing environment. What should you do?

    * A. Use gcloud to deploy the application to a new performance testing GCP project by specifying the –project parameter. Select Yes when prompted for confirmation on creating a new project.
    * B. Create a new GCP project for the performance testing environment using gcloud and deploy your App Engine application to the new GCP project.
    * C. Configure a Deployment Manager YAML template to copy the application from the development GCP project into the performance testing GCP project.
    * D. Create a new GCP project for the performance testing environment using gcloud and copy the application from the development GCP project into the performance testing GCP project.

7. Your company has a number of GCP projects that are managed by the respective project teams. Your expenditure of all GCP projects combined has exceeded your operational expenditure budget. At a review meeting, it has been agreed that your finance team should be able to set budgets and view the current charges for all projects in the organization but not view the project resources; and your developers should be able to see the Google Cloud Platform billing charges for only their own projects as well as view resources within the project. You want to follow Google recommended practices to set up IAM roles and permissions. What should you do?

    * A. **Add the finance team to the Billing Account Administrator role for each of the billing accounts that they need to manage. Add the developers to the Viewer role for the Project.**
    * B. Add the finance team to the Viewer role for the Project. Add the developers to the Security Reviewer role for each of the billing accounts.
    * C. Add the finance team to the default IAM Owner role. Add the developers to a custom role that allows them to see their own spend only.
    * D. Add the developers and finance managers to the Viewer role for the Project.

8. Your team manages the game backend for a popular game with users all over the world. The game backend APIs runs on a feet of VMs behind a Managed Instance Group (MIG) with autoscaling enabled. You have configured the scaling policy on the MIG to add more instances if the CPU utilization is consistently over 85%, and to scale down when the CPU utilization is consistently lower than 65%. You noticed the autoscaler adds more VMs than is necessary duringthe scale-up, and you suspect this might be down to an incorrect configuration in the healthcheck – the initial delay on the health check is 30 seconds. Each VM takes just under 3 minutes before it is ready to process the requests from the web application and mobile app. What should you do to fix the scaling issue?

    * A. **Update the Managed Instances template to set the maximum instances to 5.**
    * B. Update the Managed Instances template to set the maximum instances to 1.
    * C. Update the autoscaling health check from HTTP to TCP.
    * D. Update the autoscaling health check to increase the initial delay to 200 seconds.

9. You are the Cloud Security Manager at your company, and you want to review IAM users and their assigned roles in the production GCP project. You want to follow Google recommended practices. What should you do?

    * A. Review the information in the Roles section for the production GCP project in Google Cloud Console.
    * B. Check the output of gcloud iam roles list command.
    * C. Check the output of gcloud iam service-accounts list command.
    * D. **Review the information in the IAM section for the production GCP project in Google Cloud Console.**
