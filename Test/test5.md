# Google Associate Cloud Engineer Practice 
# Exam Part - 3

1. You want to deploy a cost-sensitive application to Google Cloud Compute Engine. You want the application to be up at all times, but because of the cost-sensitive nature of the application, you only want to run the application in a single VM instance. How should you configure the managed instance group?__[REVISAR]__

    * A. Enable autoscaling on the Managed Instance Group (MIG) and set minimum instances to 1 and maximum instances to 2.
    * B. Disable autoscaling on the Managed Instance Group (MIG) and set mininum instances to 1 and maximum instances to 1.
    * C. Disable autoscaling on the Managed Instance Group (MIG) and set mininum instances to 1 and maximum instances to 2.
    * D. **Enable autoscaling on the Managed Instance Group (MIG) and set minimum instances to 1 and maximum instances to 1.**

2. You are migrating a mission-critical HTTPS Web application from your on-premises data centre to Google Cloud, and you need to ensure unhealthy compute instances within the autoscaled Managed Instances Group (MIG) are recreated automatically. What should you do?__[REVISAR]__

    * A. Deploy Managed Instance Group (MIG) instances in multiple zones.
    * B. When creating the instance template, add a startup script that sends server status to Cloud Monitoring as a custom metric.
    * C. Add a metadata tag to the Instance Template with key: healthcheck value: enabled.
    * D. **Configure a health check on port 443 when creating the Managed Instance Group (MIG).**

3. Your organization specializes in helping other companies detect if any pages on their website do not align to the specifed standards. To do this, your company has deployed a custom C++ application in your on-premises data centre that crawls all the web pages of a customer’s website,compares the headers and template to the expected standard and stores the result before moving on to another customer’s website. This testing takes a lot of time and has resulted in it missing out on the SLA several times recently. The application team is aware of the slow processing time and wants to run the application on multiple virtual machines to split the load, but there is no free space in the data centre. You have been asked to identify if it is possible to migrate this application to Google cloud, ensuring it can autoscale with minimal changes and reduce the processing time. What GCP service should you recommend?

    * A. Deploy the application on Google App Engine Standard service.
    * B. Deploy the application as Cloud Dataproc job based on Hadoop.
    * C. **Deploy the application on a GCE Managed Instance Group (MIG) with autoscaling enabled.**
    * D. Deploy the application on a GCE Unmanaged Instance Group. Front the group with a network load balancer.

4. You want to migrate a public NodeJS application, which serves requests over HTTPS, from your on-premises data centre to Google Cloud Platform. You plan to host it on a feet of instances behind Managed Instances Group (MIG) in Google Compute Engine. You need to configure a GCP load balancer to terminate SSL session before passing trafic to the VMs. Which GCP Load balancer should you use?

    * A. Use External SSL proxy load balancer.
    * B. **Use HTTP(S) load balancer.**
    * C. Use Internal TCP load balancer.
    * D. Use External TCP proxy load balancer.

5. You host a production application in Google Compute Engine in the us-central1-a zone. Your application needs to be available 24*7 all through the year. The application sufered an out age recently due to a Compute Engine out age in the zone hosting your application. Your application is also susceptible to slowness during peak usage. You have been asked for a recommendation on how to modify the infrastructure to implement a cost-efective and scalable solution that can with stand zone failures. What would you recommend?__[REVISAR]__

    * A. Use Unmanaged instance groups across multiple zones. Enable Autoscaling on the Unmanaged instance group.
    * B. Use Managed instance groups with instances in a single zone. Enable a Autoscaling onthe Managed instance group.
    * C. **Use Managed instance groups across multiple zones. Enable Autoscaling on the Managed instance group.**
    * D. Use Managed instance groups with preemptible instances across multiple zones. Enable Autoscaling on the Managed instance group.

6. A mission-critical application running on a Managed Instance Group (MIG) in Google Cloud has been having scaling issues. Although the scaling works, it is not quick enough, and users experience slow response times. The solution architect has recommended moving to GKE to achieve faster scaling and optimize machine resource utilization. Your colleague containerized the application and provided you with a Dockerfile. You now need to deploy this in a GKE cluster.How should you do it?

    * A. Deploy the application using gcloud app deploy .
    * B. Deploy the application using kubectl app deploy .
    * C. Build a container image from the Docker􀃕le and push it to Google Cloud Storage (GCS).Create a Kubernetes Deployment YAML file and have it use the image from GCS. Use kubectl apply -f deployment.YAML > to deploy the application to the GKE cluster.
    * D. **Build a container image from the Dockerfile and push it to Google Container Registry (GCR). Create a Kubernetes Deployment YAML file and have it use the image from GCR. Use kubectl apply -f to deploy the application to the GKE cluster.**

7. Your company retains all its audit logs in BigQuery for 10 years. At the annual audit every year, you need to provide the auditors’ access to the audit logs. You want to follow Google recommended practices. What should you do?

    * A. Grant the auditors’ group custom IAM roles with specific permissions.
    * B. Grant the auditors’ user accounts roles/logging.viewer and roles/bigquery.dataViewer IAM roles.
    * C. **Grant the auditors’ group roles/logging.viewer and roles/bigquery.dataViewer IAM roles.**
    * D. Grant the auditors’ user accounts custom IAM roles with specific permissions.

8. You are working for a crypto currency startup, and you have enabled a link to the company’s Initial Coin Offering (ICO) white paper on the company website – which runs of Google Cloud Storage. Your CTO clicked on this link and got prompted to save the file to their desktop. The CTO thinks this is a poor user experience and has asked you to identify if it is possible to render the file directly in the browser for all users. What should you do?

    * A. **Add a metadata tag on all the PDF file objects with key: Content- Type and value:application/pdf.**
    * B. Modify the bucket ACLs to make all PDF files public.
    * C. Add a label on the Cloud Storage bucket with key: Content-Type and value:application/pdf.
    * D. Use Cloud CDN to front the static bucket and set the HTTP header display In Browser to 1.

10. You want to reduce storage costs for infrequently accessed data. The data will still be accessed approximately once a month and data older than 2 years is no longer needed. What should you do to reduce storage costs? (Select 2)__[REVISAR]__

    * A. Set an Object Lifecycle Management policy to change the storage class to Archive for data older than 2 years.
    * B. Set an Object Lifecycle Management policy to change the storage class to Coldline for data older than 2 years.
    * C. **Store infrequently accessed data in a Nearline bucket.**
    * D. **Set an Object Lifecycle Management policy to delete data older than 2 years.**
    * E. Store infrequently accessed data in a Multi-Regional bucket.

12. You want to migrate a mission-critical application from the on-premises data centre to Google Cloud Platform. Due to the mission-critical nature of the application, you want to have 3 idle (unoccupied) instances all the time to ensure the application always has enough resources to handle sudden bursts in traffic. How should you configure the scaling to meet this requirement?__[REVISAR]__

    * A. Start with 3 instances and manually scale as needed.
    * B. Enable Basic Scaling and set maximum instances to 3.
    * C. Enable Basic Scaling and set minimum instances to 3.
    * D. **Enable Automatic Scaling and set minimum idle instances to 3.**
        > *google cloud app engine - appengine-web.xml*
        > *The automatic_scaling* element sets minimum and maximum levels for number of instances, latency, and concurrent connections for a module.
        > *min-idle-instances*.- The number of instances to be kept running and ready to serve traffic.This setting only applies to the version that receives most of the traffic.

13. Your company owns a mobile game that is popular with users all over the world. The mobile game backend uses Cloud Spanner to store user state. An overnight job exports user state to a Cloud Storage bucket. The app pushes all time-series events during the game to a streaming Dataflow service that saves them to Cloud Bigtable. You are debugging an in-game issue raised by a gamer, and you want to join the user state information with data stored in Bigtable to debug. How can you do this one-off join eficiently?__[REVISAR]__

    * A. **Create two external tables in BigQuery and link them to the Cloud BigTable and Cloud Storage data sources, respectively. Execute a query in BigQuery console to join up data between the two external tables for the specific gamer.**
    * B. Set up a Cloud Dataflow job to read data from Cloud Spanner and Cloud BigTable for the specific gamer.
    * C. Set up a Cloud Dataflow job to read data from Cloud Storage and Cloud BigTable for the specific gamer.
    * D. Set up a Cloud Dataproc Cluster to run a Hadoop job to join up data from Cloud BigTableand Cloud Storage for the speci􀃕c gamer.

14. Your finance department wants you to create a new billing account and link all development and test Google Cloud Projects to the new billing account. What should you do?

    * A. Ask your security administrator to grant you the Billing Account Creator role on the GCP organization and Project Billing Manager role on all the development and test projects. Link all the development and test projects to an existing Billing Account.
    * B. **Ask your security administrator to grant you the Billing Account Creator role on the GCP organization and Project Billing Manager role on all the development and test projects.Create a new Billing Account and link all the development and test projects to the new Billing Account.**
    * C. Ask your security administrator to grant you the Billing Account Administrator role on the existing Billing Account. Create new development and test projects and link them to the existing Billing Account.
    * D. Ask your security administrator to grant you the Billing Account Administrator a role on the existing Billing Account Link all development and test projects to the existing Billing Account.

15. You have annual audits every year and you need to provide external auditors access to the last 10 years of audit logs. You want to minimize the cost and operational overhead while following Google recommended practices. What should you do?__[REVISAR]__

    * A. Set a custom retention of 10 years in Stackdriver logging and provide external auditors view access to Stackdriver Logs.
    * B. Export audit logs to Cloud Filestore via a Pub/Sub export sink.
    * C. **Export audit logs to Cloud Storage via an audit log export sink.**
    * D. Export audit logs to BigQuery via an audit log export sink.
    * E. **Grant external auditors Storage Object Viewer role on the logs storage bucket.**
    * F. **Configure a lifecycle management policy on the logs bucket to delete objects older than 10 years**

16. You have been asked to create a new Kubernetes Cluster on Google Kubernetes Engine that can autoscale the number of worker nodes as well as pods. What should you do? (Select 2)__[REVISAR]__

    * A. Create Compute Engine instances for the workers and the master and install Kubernetes.Rely on Kubernetes to create additional Compute Engine instances when needed.
    * B. **Enable Horizontal Pod Autoscaling for the Kubernetes deployment.**
        > kubectl autoscale deployment nginx --cpu-percent=50 --min=1 --max=10

        > kubectl get hpa

        NAME|REFERENCE|TARGETS|   MINPODS|MAXPODS|REPLICAS|AGE
        ---|---|---|---|---|---|---
        nginx|Deployment/nginx |0%/50%|1|10|3|61s

        > kubectl get hpa nginx -o yaml

        > kubectl delete hpa nginx
    * C. Create a GKE cluster and enable autoscaling on the instance group of the cluster.
    * D. Configure a Compute Engine instance as a worker and add it to an unmanaged instancegroup. Add a load balancer to the instance group and rely on the load balancer to createadditional Compute Engine instances when needed.
    * E. **Create a GKE cluster and enable autoscaling on Kubernetes Engine.**
        > gcloud container clusters create [CLUSTER_NAME] --num-nodes 30 --enable-autoscaling --min-nodes 15 --max-nodes 50 [--zone [COMPUTE_ZONE]]

17. Your company wants to move all documents from a secure internal NAS drive to a Google Cloud Storage (GCS) bucket. The data contains personally identiflable information (PII) and sensitive customer information. Your company tax auditors need access to some of these documents. What security strategy would you recommend on GCS?

    * A. Create randomized bucket and object names. Enable public access, but only provid especific file URLs to people who do not have Google accounts and need access.
    * B. Use signed URLs to generate time-bound access to objects.
    * C. **Grant no Google Cloud Identity and Access Management (Cloud IAM) roles to users, and use granular ACLs on the bucket.**
        > gsutil acl ch -g admins@example.com:R gs://example-bucket/
    * D. Grant IAM read-only access to users, and use default ACLs on the bucket.

18. Users of your application are complaining of slowness when loading the application. You realize the slowness is because the App Engine deployment serving the application is deployed in us-central where as all users of this application are closest to europe-west3. You want to change the region of the App Engine application to europe-west3 to minimize latency. What’s the best way to change the App Engine region?

    * A. **Create a new project and create an App Engine instance in europe-west3**
        > gcloud projects create my-new-proj-8 --region=europe-west3 
        
        > gcloud app deploy -f app.yaml --project=my-new-proj-8
    * B. Use the gcloud app region set command and supply the name of the new region.
    * C. From the console, under the App Engine page, click edit, and change the region drop-down.
    * D. Contact Google Cloud Support and request the change.

19. You are developing a mobile game that uses Cloud Datastore for gaming leader boards and player profiles. You want to test an aspect of this solution locally on your Ubuntu workstation which already has Cloud SDK installed. What should you do?

    * A. **Install Datastore emulator to provide local emulation of the production datastore environment in your  local workstation by running gcloud components install.**
        > gcloud beta emulators datastore start [flags]
    * B. Install Datastore emulator to provide local emulation of the production datastore aenvironment in your local workstation by running apt get install.
    * C. Add a new index to Cloud Datastore instance in the development project by running gcloud datastore indexes create and modify your application on your workstation to retrieve the data from Cloud Datastore using the index.
    * D. Initiate an export of Cloud Datastore instance from development GCP project by executing gcloud datastore export. Modify your applications to point to the export.

20. You deployed a number of services to Google App Engine Standard. The services are designed as microservices with several interdependencies between them. Most services have few version upgrades but some key services have over 20 version upgrades. You identifed an issue with the service pt-createOrder and deployed a new version v3 for this service. You are confident this works and want this new version to receive all traffic for the service. You want to minimize efort and ensure the availability of service. What should you do?

    * A. Execute gcloud app versions stop v2 –service=”pt-createOrder” and gcloud app versions start v3 –service=”pt-createOrder”
    * B. Execute gcloud app versions migrate v3
    * C. Execute gcloud app versions stop v2 and gcloud app versions start v3
    * D. **Execute gcloud app versions migrate v3 --service  “pt-createOrder”**

21. You have a web application deployed as a managed instance group based on an instance template. You modifed the startup script used in the instance template and would like the existing instances to pick up changes from the new startup scripts. Your web application is currently serving live web traffic. You want to propagate the startup script changes to all instances in the managed instances group while minimizing effort, minimizing cost and ensuring that the available capacity does not decrease. What would you do?__[REVISAR]__

    * A. Create a new managed instance group (MIG) based on a new template. Add the group to the backend service for the load balancer. When all instances in the new    are healthy, delete the old managed instance group.
    * B. Delete instances in the managed instance group (MIG) one at a time and rely on auto-healing to provision an additional instance.
    * C. Perform a rolling-action start-update with max-unavailable set to 1 and max–surge set to 0.
    * D. **Perform a rolling-action replace with max-unavailable set to 0 and max-surge set to 1.**
        > gcloud compute instance-groups managed rolling-action start-update [INSTANCE_GROUP_NAME] --version=template=[NEW_TEMPLATE] --min-ready=3m --max-unavailable=1 --max-surge=0 [--zone=ZONE | --region=REGION]
23. To facilitate disaster recovery, your company wants to save database backup tar files in Cloud Storage bucket. You want to minimize the cost. Which GCP Cloud Storage class should you use?__[REVISAR]__

    * A. **Use Coldline Storage Class.**
    * B. Use Multi-Regional Storage Class.
    * C. Use Regional Storage Class.
    * D. Use Nearline Storage Class.

24. You recently deployed a new application in Google App Engine to serve production traffic.After analyzing logs for various user flows, you uncovered several issues in your application code and have developed a fix to address the issues. Parts of your proposed fix could not be validated in the pre-production environment by your testing team as some of the scenarios can only be validated by an end-user with access to specific data in your production environment. In the company’s weekly Change Approval Board meeting, concerns were raised that the fix could possibly take down the application. It was unanimously agreed that while the fix is risky, it is a necessary change to the application. You have been asked to suggest a solution that minimizes the impact of the change going wrong. You also want to minimize costs. What should you do?

    * A. Set up a second Google App Engine service, and then update a subset of clients to hit the new service.
    * B. Deploy the new application version temporarily, capture logs and then roll it back to the previous version.
    * C. **Deploy a new version of the application, and use traffic splitting to send a small percentage of traffic to it.**
        > gcloud app services set-traffic [MY_SERVICE] --splits [MY_VERSION1]=[VERSION1_WEIGHT],[MY_VERSION2]=[VERSION2_WEIGHT] --split-by [IP_OR_COOKIE]
    * D. Create a second Google App Engine project with the new application code, and on board users gradually to the new application.

25. You want to list all the compute instances in zones us-central1-b and europe-west1-d. Which of the commands below should you run to retrieve this information?

    * A. **gcloud compute instances list –-filter=”zone:(us-central1-b europe-west1-d)”**
    * B. gcloud compute instances get –-filter=”zone:(us-central1-b)” and gcloud computeinstances list -􀃕lter= “zone:( europe-west1-d)” and combine the results.
    * C. gcloud compute instances list –-filter=”zone:(us-central1-b)” and gcloud compute instances list --filter=”zone:(europe-west1-d)” and combine the results.
    * D. gcloud compute instances get –-filter=”zone:(us-central1-b europe-west1-d)”

26. A production application serving live traffic needs an important update deployed gradually.The application is deployed in a Managed Instance Group (MIG) in the US-Central region. The application receives millions of requests each minute, and you want to patch the application while ensuring the number of instances (capacity) in the Managed Instance Group (MIG) does not decrease. What should you do?__[REVISAR]__

    * A. Carry out a rolling update by executing gcloud compute instance-groups rolling-actionstart-update –max-surge 0 -max-unavailable 1.
    * B. Deploy the update in a new MIG and add it as a backend service to the existing production Load Balancer. Once all instances in the new group have warmed up, remove the old MIG from the Load Balancer backend and delete the group.
    * C. **Carry out a rolling update by executing gcloud compute instance-groups rolling-action start-update -max-surge 1 -max-unavailable 0.**
    * D. Update the existing Managed Instance Group (MIG) to point to a new instance template containing the updated version. Terminate all existing instances in the MIG and wait until they are all replaced by new instances created from the new template.

27. You want to create a new role and grant it to the SME team. The new role should provide your SME team BigQuery Job User and Cloud Bigtable User roles on all projects in the organization. You want to minimize operational overhead. You want to follow Google recommended practices.How should you create the new role?

    * A. Execute command gcloud iam combineroles –global to combine the 2 roles into a newcustom role and grant them globally to SME team group.
    * B. In GCP Console under IAM Roles, select both roles and combine them into a new custom role. Grant the role to the SME team group at project. Use gcloud iam promote-role topromote the role to all other projects and grant the role in each project to the SME team group.   
    * C. In GCP Console under IAM Roles, select both roles and combine them into a new custom role. Grant the role to the SME team group at project. Repeat this step for each project.
    * D. **In GCP Console under IAM Roles, select both roles and combine them into a new custom role. Grant the role to the SME team group at the organization level.**

28. Your company runs all its applications in us-central1 region in a single GCP project and single VPC. The company has recently expanded its operations to Europe, but customers in the EU are complaining about slowness accessing the application. Your manager has requested you to deploy a new instance in the same project in europe-west1 region to reduce latency to the EU customers. The newly deployed VM needs to reach a central Citrix Licensing Server in us-central-1. How should you design the network and firewall rules while adhering to Google Recommended practices?__[REVISAR]__

    * A. Deploy the VM in a new subnet in europe-west1 region in a new VPC. Peer the two VPC sand have the VM contact the Citrix Licensing Server on its internal IP Address.
    * B. Deploy the VM in a new subnet in europe-west1 region in the existing VPC. Peer the two subnets using Cloud VPN. Have the VM contact the Citrix Licensing Server on its internal IPAddress.
    * C. Deploy the VM in a new subnet in europe-west1 region in a new VPC. Set up an HTTP(s)Load Balancer for the Citrix Licensing Server and have the VM contact the Citrix Licensing Server through the Load Balancer’s public address.
    * D. **Deploy the VM in a new subnet in europe-west1 region in the existing VPC. Have the VM contact the Citrix Licensing Server on its internal IP Address.**

30. Your company stores customer PII data in Cloud Storage buckets. A subset of this data is regularly imported into a BigQuery dataset to carry out analytics. You want to make sure the access to this bucket is strictly controlled. Your analytics team needs read access on the bucket so that they can import data in BigQuery. Your operations team needs read/write access to both the bucket and BigQuery dataset to add Customer PII data of new customers on an on going basis.Your Data Vigilance offcers need Administrator access to the Storage bucket and BigQuery dataset. You want to follow Google recommended practices. What should you do?__[REVISAR]__

    * A. At the Project level, add your Data Vigilance ofecers user accounts to the Owner role, add your operations team user accounts to the Editor role, and add your analytics team user accounts to the Viewer role.
    * B. **Use the appropriate predefined IAM roles for each of the access levels needed for Cloud Storage and BigQuery. Add your users to those roles for each of the services.**
    * C. At the Organization level, add your Data Vigilance offcers user accounts to the Owner role, add your operations team user accounts to the Editor role, and add your analytics team user accounts to the Viewer role.
    * D. Create 3 custom IAM roles with appropriate permissions for the access levels needed for Cloud Storage and BigQuery. Add your users to the appropriate roles.

31. Your company has deployed a wide range of application across several Google Cloud projects in the organization. You are a security engineer within the Cloud Security team, and an apprentice has recently joined your team. To gain a better understanding of your company’s Google cloud estate, the apprentice has asked you to provide them access which lets them have detailed visibility of all projects In the organization. Your manager has approved the request but has asked you to ensure the access does not let them edit/write access to any resources. Which IAM roles should you assign to the apprentice?

    * A. **Grant roles/resourcemanager.organizationViewer and roles/viewer.**
    * B. Grant roles/resourcemanager.organizationAdmin and roles/browser.
    * C. Grant roles/resourcemanager.organizationViewer and roles/owner.
    * D. Grant roles/owner and roles/networkmanagement.admin.

32. You created an update for your application on App Engine. You want to deploy the update without impacting your users. You want to be able to roll back as quickly as possible if it fails.What should you do?

    * A. Deploy the update as the same version that is currently running. If the update fails,redeploy your older version using the same version identi􀃕er.
    * B. **Deploy the update as a new version. Migrate traffic from the current version to the new version. If it fails, migrate the traffic back to your older version.**
    * C. Deploy the update as the same version that is currently running. You are con􀃕dent theupdate works so you don’t plan for a rollback strategy.
    * D. Notify your users of an upcoming maintenance window and ask them not to use yourapplication during this window. Deploy the update in that maintenance window.

33. You are designing a mobile game which you hope will be used by numerous users around the world. The game backend requires a Relational DataBase Management System __(RDBMS)__ for persisting game state and player profiles. You want to select a database that can __scale to a global audience with minimal configuration updates__. Which database should you choose?__[REVISAR]__

    * A. Cloud SQL.
    * B. **Cloud Spanner.**
    * C. Cloud Datastore.
    * D. Cloud Firestore.

34. Your company stores sensitive user information (PII) in three multi-regional buckets in US,Europe and Asia. All three buckets have data access logging enabled on them. The compliance team has received reports of fraudulent activity and has begun investigating a customer care representative. It believes the specific individual may have accessed some objects they are not authorized to and may have added labels to some files in the buckets to enable favourable discounts for their friends. The compliance team has asked you to provide them with a report of activities for this customer service representative on all three buckets. How can you do this eficiently?

    * A. Enable a Cloud Trace on the bucket and wait for the user to access objects/set metadata to capture their activities.
    * B. Retrieve this information from Activity logs in GCP Console.
    * C. Retrieve this information from the Cloud Storage bucket page in GCP Console.
    * D. **Apply the necessary filters in Cloud Logging Console to retrieve this information.**

35. Your company’s new mobile game has gone live, and you have transitioned the backend application to the operations team. The mobile game uses Cloud Spanner to persist game state,leader board and player profile. All operations engineers __require access to view and edit table data__ to support runtime issues. What should you do?

    * A. **Grant roles/spanner.databaseUser IAM role to all operations engineers group.**
    * B. Grant roles/spanner.viewer IAM role to all operations engineers group.
    * C. Grant roles/spanner.viewer IAM role to all operations engineers user accounts.
    * D. Grant roles/spanner.databaseUser IAM role to all operations engineers user accounts.

36. You have one GCP project with default region and zone set to us-east1 and us-east1-b respectively. You have another GCP project with default region and zone set to us-west1 and us-west1-a respectively. You want to provision a VM in each of these projects eficiently using gcloud CLI. What should you do?

    * A. Execute gcloud config configuration create [config name] to create two configurations,one for each project. Execute gcloud configurations list to create and start the VMs.
    * B. **Execute gcloud config configuration create [config name] to create two configurations,one for each project. Execute gcloud config con􀃕gurations activate [config name] to activate the first configuration, and gcloud compute instances create to create the VM. Repeat the steps for other configuration.**
    * C. Execute gcloud configurations activate [config name] to activate the configuration for each project and execute gcloud configurations list to create and start the VM.
    * D. Execute gcloud configurations activate [config name] to activate the configuration for each project and execute gcloud config list to create and start the VM.

37. You want to create a Google Cloud Storage regional bucket logs-archive in the Los Angeles region (us-west2). You want to use Coldline storage class to minimize costs and you want to retain files for 10 years. Which of the following commands should you run to create this bucket?

    * A. gsutil mb t us-west2 -S nearline -retention 10y gs://logs-archive
    * B. gsutil mb -l los-angeles -S coldline -retention 10m gs://logs-archive
    * C. gsutil mb – us-west2 -S coldline – -retention 10m gs://logs-archive
    * D. **gsutil mb – us-west2 -S coldline -retention 10y gs://logs-archive**

38. You developed a web application that lets users upload and share images. You deployed this application in Google Compute Engine and you have configured Stackdriver Logging. Your application sometimes times out while uploading large images, and your application generates relevant error log entries that are ingested to Stackdriver Logging. You would now like to create alerts based on these metrics. You intend to add more compute resources manually when the number of failures exceeds a threshold. What should you do in order to alert based on these metrics with minimal effort?__[REVISAR]__

    * A. **Add the Stackdriver monitoring and logging agent to the instances running the code.**
    * B. In Stackdriver logging, create a new logging metric with the required filters, edit the application code to set the metric value when needed, and create an alert in Stackdriver based on the new metric.
    * C. In Stackdriver Logging, create a custom monitoring metric from log data and create an alert in Stackdriver based on the new metric.
    * D. Create a custom monitoring metric in code, edit the application code to set the metricvalue when needed, create an alert in Stackdriver based on the new metric.

39. Your company stores sensitive PII data in a cloud storage bucket. The objects are currently encrypted by Google-managed keys. Your compliance department has asked you to ensure all current and future objects in this bucket are encrypted by customer-managed encryption keys.You want to minimize effort. What should you do?__[REVISAR]__

    * A.  
        - 1. In the bucket advanced settings, select the Customer-managed key and then select a Cloud KMS encryption key. 
        - 2. Existing objects encrypted by Google-managed keys can still be decrypted by the new Customer-managed key.
    * B. 
        - 1. **In the bucket advanced settings, select the Customer-managed key and then select a Cloud KMS encryption key.**
        - 2. **Rewrite all existing objects using gsutil rewrite to encrypt them with the new Customer-managed key.**
    * C. 
        - 1. In the bucket advanced settings, select the customer-supplied key and then select a Cloud KMS encryption key. 
        - 2. Delete all existing objects and upload them again so they use the new customer-supplied key for encryption.
    * D.
        - 1. Rewrite all existing objects using gsutil rewrite to encrypt them with the new Customer-managed key.
        - 2. In the bucket advanced settings, select the Customer-managed key andthen select a Cloud KMS encryption key.

40. You have two compute instances in the same VPC but in different regions. You can SSH from one instance to another instance using their internal IP address but not their external IP address.What could be the reason for SSH failing on external IP address?__[REVISAR]__

    * A. The external IP address is disabled.
    * B. The compute instances are not using the right cross-region SSH IAM permissions
    * C. The compute instances have a static IP for their external IP.
    * D. **The combination of compute instance network tags and VPC firewall rules only allow SSH from the subnets IP range.**

41. Your colleague updated a deployment manager template of a production application serving live traffic. You want to deploy the update to the live environment later during the night when user traffic is at its lowest. The git diff on the pull request shows the changes are substantial and you would like to review the intended changes without applying the changes in the live environment. You want to do this as eficiently and quickly as possible. What should you do?__[REVISAR --preview]__

    * A. **Preview the changes by applying the deployment manager template with the –preview flag.**
    * B. Add logging statements in the deployment manager template YAML file.
    * C. Clone the GCP project and apply the deployment manager template in the new project. Review the actions in Cloud Logging and monitor for failures before applying the templatein the production GCP project.
    * D. Apply the deployment manager template and review the actions in Cloud Logging.

42. You have asked your supplier to send you a purchase order and you want to enable them to upload the file to a cloud storage bucket within the next 4 hours. Your supplier does not have a Google account. You want to follow Google recommended practices. What should you do?__[REVISAR]__

    * A. **Create a service account with just the permissions to upload files to the bucket. Create a JSON key for the service account. Execute the command gsutil signurl -m PUT -d 4h gs:///++ .**
    * B. Create a service account with just the permissions to upload files to the bucket. Create a JSON key for the service account. Execute the command gsutil signurl – -d 4h gs:///.
    * C. Create a service account with just the permissions to upload files to the bucket. Create a JSON key for the service account. Execute the command gsutil signurl httpMethod PUT-d4hgs:///**.
    * D. Create a JSON key for the Default Compute Engine Service Account. Execute the command gsutil signurl -m PUT -d 4h gs://kbucket>/**.

44. Your organization is planning the infrastructure for a new large-scale application that will need to store anything between 200 TB to a petabyte of data in NoSQL format for Low-latency read/write and High-throughput analytics. Which storage option should you use?

    * A. Cloud Spanner.
    * B. **Cloud Bigtable.**
    * C. Cloud Datastore.
    * D. Cloud SQL

45. You have a collection of audio/video files over 80GB each that you need to migrate to GoogleCloud Storage. The files are in your on-premises data center. What migration method can you use to help speed up the transfer process?__[REVISAR]__

    * A. Start a recursive upload.
    * B. **Use parallel uploads to break the file into smaller chunks then transfer it simultaneously.**
    * C. Use the Cloud Transfer Service to transfer.
    * D. Use multithreaded uploads using the -m option.

46. Your company has chosen to go serverless to enable developers to focus on writing code without worrying about infrastructure. You have been asked to identify a GCP Serverless service that does not limit your developers to specific runtimes. In addition, some of the applications need __WebSockets support__. What should you suggest?__[REVISAR]__

    * A. **Cloud Run for Anthos**
    * B. Cloud Functions
    * C. App Engine Standard
    * D. Cloud Run

47. Your company wants to move 200 TB of your website click stream logs from your on-premise data center to Google Cloud Platform. These logs need to be retained in GCP for compliance requirements. Your business analysts also want to run analytics on these logs to understand user click behavior on your website. Which of the below would enable you to meet these requirements? (Select Two)

    * A. Load logs into Google Cloud SQL
    * B. **Load logs into Google BigQuery.**
    * C. **Upload log files into Google Cloud Storage.**
    * D. Import logs into Google Stackdriver.
    * E. Insert logs into Google Cloud Bigtable.

48. Your team created two networks (VPC) with non-overlapping ranges in Google Cloud in the same region. The first VPC hosts an encryption service on a GKE cluster with cluster autoscaling enabled The encryption service provides TCP endpoints to encrypt and decrypt data. The second VPC pt-network hosts a user management system on a single Google Cloud Compute Engine VM.The user management system deals with PII data and needs to invoke the encryption endpoints running on the GKE cluster to encrypt and decrypt data. What should you do to enable the compute engine VM invoke the TCP encryption endpoints while minimizing effort?__[REVISAR]__

    * A. Create a Kubernetes Service with type: NodePort to expose the encryption endpoints running in the pods. Set up a custom proxy in another compute engine VM in pt-network and configure it to forward the traffic to the Kubernetes Service in the other VPC. Have the GCE VM invoke the TCP encryption endpoints on the proxy DNS address.
    * B. Create a Kubernetes Service with type: Load balancer to expose the encryption endpoints running in the pods. Configure a Cloud Armour security policy to allow traffic from GCE VM to the Kubernetes Service. Have the GCE VM invoke the TCP encryption endpoints on the Kubernetes Service DNS address.
    * C. Create a Kubernetes Service with type: Load balancer to expose the encryption endpoints running in the pods. Disable propagating Client IP Addresses to the pods by setting Services spec.ecternalTrafficcPolicy to Cluster. Have the GCE VM invoke the TCP encryption endpoints on the Kubernetes Service DNS address.
    * D. **Create a Kubernetes Service with type: Loadbalancer and the cloud.google.com/lood-balancer-type: Internal annotation to expose the encryption endpoints running in the pods.Peer the two VPCs and have the GCE VM invoke the TCP encryption endpoints on the (internal) Kubernetes Service DNS address.**

49. You deployed a Python application to GCP App Engine Standard service in the us-central region. Most of your customers are based in Japan and are experiencing slowness due to the latency. You want to transfer the application from us-central region to asia-northeast1 region to minimize latency. What should you do?

    * A. Update the region property to asia-northeast1 on the App Engine application.
    * B. Deploy a new app engine application in the same GCP project and set the region to asia-northeast1. Delete the old App Engine application.
    * C. **Create a new GCP project. Create a new App Engine Application in the new GCP project and set its region to asia-northeast-1. Delete the old App Engine application.**
    * D. Update the default region property to asia-northeast1 on the App Engine Service.

50. You deployed a Java application in a Google Compute Engine VM that has 3.75 GB Memory and 1 vCPU. At peak usage, the application experiences __java.lang.OutOfMemory__ errors that take down the application entirely and requires a restart. The CPU usage at all times is minimal. Your operations team have asked you to increase the memory on the VM instance to 8 GB. You want todo this while minimizing the cost. What should you do?__[REVISAR]__

    * A. **Stop the compute engine instance, update the memory on the instance to 8 GB and start the compute engine instance.**
    * B. Make use of the live-migration feature of Google Compute Engine to migrate the application to another instance with more memory.
    * C. Stop the compute engine instance, update the machine to n1-standard-2 and start the compute engine instance.
    * D. Add a metadata tag to the instance with key: new-memory-size and value: 8GB.
