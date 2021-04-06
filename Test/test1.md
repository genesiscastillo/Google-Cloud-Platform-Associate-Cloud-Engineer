# Google Associate Cloud Engineer Practice 
# Exam Part - 7

1. Your company stores terabytes of image thumbnails in Google Cloud Storage bucket with versioning enabled. An engineer deleted a current (live) version of an image and a non-current(not live) version of another image. What is the outcome of this operation?

    * A. The deleted current version becomes a non-current version, and a lifecycle rule is applied to delete after 30 days. A lifecycle rule is applied on the deleted non-current version to delete after 30 days.
    * B. The deleted current version becomes a non-current version, and a lifecycle rule is applied to transition to Nearline Storage after 30 days. A lifecycle rule is applied on the deleted non-current version to transition to Nearline Storage after 30 days.
    * C. The deleted current version is deleted permanently. The deleted non-current version is deleted permanently.
    * D. **The deleted current version becomes a non-current version. The deleted non-current version is deleted permanently.**

10. Your company has terabytes of audit logs and analytics data in multiple BigQuery datasets.Some of these data sets need to be retained long term for audit purposes. You want to ensure analysts do not delete this data. What should you do?__[REVISAR]__

    * A. Grant a custom role with just the required query permissions to all the analysts.
    * B. Grant roles/bigquery.dataOwner IAM role to the analysts’ group.
    * C. **Grant roles/bigquery.user IAM role to the analysts’ group.**
    * D. Grant a custom role with just the required query permissions to the analysts’ group.

11. You developed a new mobile game that uses Cloud Spanner for storing user state, player profile and leader board. Data is always accessed by using the primary key. Your performance testing team identifed latency issues in the application, and you suspect it might be related to table primary key configuration. You created the table by executing this DDL:

1. CREATE TABLE users {
user_id INT64 NOT NULL,
user_name STRING (255),
email_address STRING (255)
} PRIMARY KEY (user_id)

What should you do to fix this read latency issue?

   * A. Add another index on user_id column to speed up the data retrieval.
   * B. Make the table smaller by removing email_address and add another index on user_id column to speed up the data retrieval.
   * C. Make the table smaller by removing email_address.
   * D. **Update the primary key (user_id) to not have sequential values.**

12. There has been an increased phishing email activity recently, and you deployed a new application on a GKE cluster to help scan and detect viruses in uploaded files. Each time the Finance or HR department receive an email with an attachment, they use this application to scan the email attachment for viruses. The application pods open the email attachment in a sandboxed environment before initiating a virus scan. Some infected email attachments may run arbitrary phishing code with elevated privileges in the container. You want to ensure that the pods that run these scans do not impact pods of other applications running in the same GKE cluster. How can you achieve this isolation between pods?__[REVISAR]__

    * A. Detect vulnerabilities in the application container images in GCR repo by using the Container Analysis API.
    * B. **Create a new (non-default) node pool with sandbox type set to gvisor and configure the deployment spec with a runtime ClassName of gvisor.**
    * C. Configure the pods to use containerd as the runtime by adding a node selector with key:cloud.google.com/gke-os-distribution and value:cos_containerd.
    * D. Have your applications use trusted container images by enabling Binary Authorization.

13. An external partner working on a production issue has asked you to share a list of all GCP API senabled for your GCP production project – production_v1. How should you retrieve this information?__[REVISAR]__

    * A. Execute gcloud services list –-available to retrieve a list of all services enabled for the project.
    * B. **Execute gcloud projects list –-filter=’name:production_vl’ to retrieve the ID of the project,and execute gcloud services list -–project to retrieve a list of all services enabled for the project.**
    * C. Execute gcloud init production_v1 to set production_v1 as the current project in gcloud configuration and execute gcloud services list --available to retrieve a list of all services enabled for the project.
    * D. Execute gcloud info to retrieve the account information and execute gcloud services list –-account to retrieve a list of all services enabled for the project.

14. Your finance team owns two GCP projects – one project for payroll applications and another project for accounts. You need the VMs in the payroll project in one VPC to communicate with VMs in accounts project in a diferent VPC and vice versa. How should you do it?

    * A. Ensure you have the Administrator role on both projects and move all instances to two new VPCs.
    * B. **Share the VPC from one of the projects and have the VMs in the other project use the shared VPC. Ensure both projects belong to the same GCP organization.**
    * C. Create a new VPC and move all VMs to the new VPC. Ensure both projects belong to thesame GCP organization.
    * D. Ensure you have the Administrator role on both projects and move all instances to asingle new VPC.

15. Your company procured a license for a third-party cloud-based document signing system for the procurement team. All members of the procurement team need to sign in with the same service account. Your security team prohibits sharing service account passwords. You have been asked to recommend a solution that lets the procurement team login as the service account in the document signing system but without the team knowing the service account password. What should you do?__[REVISAR]__

    * A. Have a single person from the procurement team access the document signing system with the service account credentials.
    * B. **Register the application as a password vaulted app and set the credentials to the service account credentials.**
    * C. Ask the third-party provider to enable OAuth 2.0 for the application and set the credentials to the service account credentials.
    * D. Ask the third-party provider to enable SAML for the application and set the credentials to the service account credentials.

16. Your company uses a legacy application that still relies on the legacy LDAP protocol to authenticate. Your company plans to migrate this application to the cloud and is looking for acost-efective solution while minimizing any developer efort. What should you do?__[REVISAR]__

    * A. Modify the legacy application to use SAML and ask users to sign in through Gmail.
    * B. Modify the legacy application to use OAuth 2.0 and ask users to sign in through Gmail.
    * C. Synchronize data within your LDAP server with Google Cloud Directory Sync.
    * D. **Use secure LDAP to authenticate the legacy application and ask users to sign in through Gmail.**

17. You developed a python application that exposes an HTTP(s) endpoint for retrieving 2-week weather forecast for a given location. You deployed the application in a single Google Cloud Compute Engine Virtual Machine, but the application is not as popular as you anticipated and has been receiving very few requests. To minimize costs, your colleague suggested containerizing the application and deploying on a suitable GCP compute service. Where should you deploy your containers?

    * A. App Engine Flexible.
    * B. GKE with horizontal pod autoscaling and cluster autoscaler enabled.
    * C. **Cloud Run.**
    * D. Cloud Run on GKE.

18. You developed a python application that gets triggered by messages from a Cloud Pub/Sub topic. Your manager is a big fan of both serverless and containers and has asked you to containerize the application and deploy on Google Cloud Run. How should you do it?__[REVISAR]__

    * A. Assign roles/pubsub.subscribei role (Pub/Sub Subscriber role) to the Cloud Run service account. Set up a Cloud Pub/Sub subscription on the topic and configure the application to pull messages.
    * B. Deploy your application to Google Cloud Run on GKE. Set up a Cloud Pub/Sub subscription on the topic and deploy a sidecar container in the same GKE cluster to consume the message from the topic and push it to your application.
    * C. **Assign roles/run.invoker role (Cloud Run Invoker role) on your Cloud Run application to aservice account. Set up a Cloud Pub/Sub subscription on the topic and configure it to use the service account to push the message to your Cloud Run application.**
    * D. Trigger a Cloud Function whenever the topic receives a new message. From the Cloud Function, invoke Cloud Run.

19. Your data warehousing team executed an Apache Sqoop job to export data from Hive/Hbase and uploaded this data in AVRO file format to Cloud Storage. The business analysts at your company have years of experience using SQL. They have asked you to identify if there is a cost-efective way to query the information in AVRO files through SQL. What should you do?__[REVISAR]__

    * A. Transfer the data from Cloud Storage to BigQuery and advise the business analysts to run their SQL queries in BigQuery.
    * B. Transfer the data from Cloud Storage to HDFS. Configure an external table in Hive to point to HDFS and advise the business analysts to run their SQL queries in Hive.
    * C. **Point a BigQuery external table at the Cloud Storage bucket and advise the business analysts to run their SQL queries in BigQuery.**
    * D. Transfer the data from Cloud Storage to Cloud Datastore and advise the business analysts to run their SQL queries in Cloud Datastore.

2. Your company wants to move all its on-premises applications to Google Cloud. Most applications depend on Kubernetes orchestration, and you have chosen to deploy these applications in Google Kubernetes Engine (GKE) in your GCP project app_prod. The security team have requested you to store all container images in Google Container Registry (GCR) in a separate project gcr_ proj, which has an automated vulnerability management scanning set up by asecurity partner. You are ready to push an image to GCR repo and want to tag it as tranquillity:v1.How should you do it?

    * A. Execute gcloud builds submit –tag gcr.io/gcr_proj/tranquillity from Cloud shell.
    * B. Execute gcloud builds submit –tag gcr.io/app_prod/tranquillity:v1 from Cloud shell.
    * C. Execute gcloud builds submit –tag gcr.io/app_prod/tranquillity from Cloud shell.
    * D. **Execute gcloud builds submit –tag gcr.io/gcr_proj/tranquillity:v1 from Cloud shell.**

20. Your company has several business-critical applications running on its on-premises data centre, which is already at full capacity, and you need to expand to Google Cloud Platform to handle traffic bursts. You want to virtual machine instances in both on-premises data centre and Google Cloud Compute Engine to communicate via their internal IP addresses. What should you do?__[REVISAR]__

    * A. Add bastion hosts in GCP as well as on-premises network and set up a proxy tunnel between the bastion hosts in GCP and the bastion hosts in the on-premises network. Allow applications in the data centre to scale to Google Cloud through the proxy tunnel.
    * B. Create a new GCP project and a new VPC and enable VPC peering between the new VPC and networks in the data centre.
    * C. **Create a new VPC in GCP with a non-overlapping IP range and configure Cloud VPN between the on-premises network and GCP.**
    * D. Allow applications in the data centre to scale to Google Cloud through the VPN tunnel.
    * E. Create a new GCP project and a new VPC and make this a shared VPC with the on-premises network. Allow applications in the data centre to scale to Google Cloud on the shared VPC.

21. The machine learning team at your company infrequently needs to use a GKE cluster with specific GPUs for processing a non-restartable and long-running job. How should you set up the GKE cluster for this requirement?

    * A. **Deploy the workload on a node pool with non-preemptible compute engine instances and GPUs attached to them. Enable cluster autoscaling and set min-nodes to 1.**
    * B. Deploy the workload on a node pool with preemptible compute engine instances and GPUs attached to them.
    * C. Enable GKE cluster node auto-provisioning.
    * D. Enable Vertical Pod Autoscaling.

22. You want to deploy an application to GKE cluster to enable the translation of mp3 files. The application uses an open source translation library that is IOPS intensive. The organization backup strategy involves taking disk snapshots of all nodes at midnight. You want to estimate the cost of running this application in GKE cluster for the next month. In addition to the node pool size,instance type, location and usage duration, what else should you fill in the GCP pricing calculator when estimating the cost of running this application?__[REVISAR]__

    * A. GPU and GKE Cluster Management Fee.
    * B. **Local SSD, Snapshot Storage and Persistent disk storage.**
    * C. GPU, Snapshot Storage and Persistent disk storage.
    * D. Local SSD and GKE Cluster Management Fee.

23. Your organization has several applications in the on-premises data centre that depend on Active Directory for user identification and authorization. Your organization is planning a migration to Google Cloud Platform and requires complete control over the Cloud Identity accounts used by staff to access Google Services and APIs. Where possible, you want to re-use Active Directory as the source of truth for identification and authorization. What should you do?

   * A. Ask all staff to create Cloud Identity accounts using their Google email address and require them to re-use their AD password for Cloud Identity account.
   * B. Create a custom script that synchronizes identities between Active Directory and Cloud Identity. Use Google Cloud Scheduler to run the script regularly.
   * C. Ask your operations team to export identities from active directory into a comma-separated file and use GCP console to import them into Cloud Identity daily.
   * D. **Synchronize users in Google Cloud Identity with identities in Active directory by running Google Cloud Directory Sync (GCDS).**

24. Your colleague is learning about docker images, containers and Kubernetes, and has recently deployed a sample application to a GKE You deployed a demo application on a GKE cluster that uses preemptible nodes. The deployment has 2 replicas, and although the demo application is responding to requests, the output from Cloud Shell shows one of the pods is pending state.
- kubectl get pods -l app=demo
What is the most likely explanation for this behaviour?

   * A. The pod in the pending state is unable to download the docker image.
   * B. The node got preempted before the pod could be started fully. GKE cluster master is provisioning a new node.
   * C. The pod in the pending state is too big to fit on a single preemptible VM. The node pool needs to be recreated with a bigger machine type.
   * D. **Cluster autoscaling is not enabled, and the existing (only) node doesn’t have enough resources for provisioning the pod.**

25. Your company stores terabytes of image thumbnails in Google Cloud Storage bucket with versioning enabled. You want to cut down the storage costs and you spoke to the image editing lab to understand their usage requirements. They inform you that they access non current versions of images at most once a month and are happy for you to archive these objects after 30 days from the date of creation, however, there may be a need to retrieve and update some of these archived objects at the end of each month. What should you do?__[REVISAR]__

    * A. Configure a lifecycle rule to transition non-current versions to Coldline Storage Classafter 30 days.
    * B. Configure a lifecycle rule to transition objects from Regional Storage Class to Coldline Storage Class after 30 days.
    * C. Configure a lifecycle rule to transition objects from Regional Storage Class to Nearline Storage Class after 30 days.
    * D. **Configure a lifecycle rule to transition non-current versions to Nearline Storage Class after 30 days.**

26. A mission-critical image processing application running in your on-premises data centre requires 64 virtual CPUs to execute all processes. You colleague wants to migrate this mission-critical application to Google Cloud Platform Compute Engine and has asked your suggestion for the instance size. What should you suggest?

    * A. Provision the compute engine instance on the default settings, then modify it to have 64 vCPUs.
    * B. Provision the compute engine instance on the default settings, then scale it as per sizing recommendations.
    * C. **Use n1-standard-64 machine type when provisioning the compute engine instance.**
    * D. Use Xeon Scalable Processor (Skylake) as the CPU platform when provisioning the compute engine instance.

27. Your company has accumulated terabytes of analytics data from click stream logs and stores this data in BigQuery dataset in a central GCP project. Analytics teams from several departments in multiple GCP projects run queries against this data. The costs for BigQuery job executions have increased drastically in recent months, and your finance team has asked your suggestions for controlling these spiralling costs. What should you do? (Select two)__[PENDIENTE : C]__

    * A. Separate the data of each department and store it in BigQuery in their GCP project. Enable BigQuery quota on a per-project basis.
    * B. Create a separate GCP project for each department and configure billing settings on each project to pick up the costs for queries ran by their analytics team.
    * C. **Move to BigQuery flat rate and purchase the required number of query slots.**
    * D. Replicate the data in all GCP projects & have each department query data from their GCP project instead of the central BigQuery project.

28. All development teams at your company share the same development GCP project, and this has previously resulted in some teams accidentally terminating compute engine resources of other teams, causing downtime and loss of productivity. You want to deploy a new application to the shared development GCP project, and you want to protect your instance from such issues. What should you do?

    * A. Deploy the application on a Preemptible VM.
    * B. **Set the deletion Protection property on the VM.**
    * C. Deploy the application on a Shielded VM.
    * D. Deploy the application on VMs provisioned on sole-tenant nodes.

29. You want to provide an operations engineer access to a specific GCP project. Everyone at your company has G Suite accounts. How should you grant access?__[REVISAR]__

    * A. Run G Suite to Cloud Identity migration tool to convert G Suite Accounts into Cloud Identity accounts. Grant the necessary roles to the Cloud Identity account.
    * B. Add the operations engineer to the gcp-console-access group in your G Suite domain and grant the necessary roles to the group.
    * C. **Assign the necessary roles to their G Suite email address.**
    * D. Disable G Suite Sign in, enable Cloud Identity Sign in, and add their email address to Cloud Identity. Grant the necessary roles to the Cloud Identity account.

3. Your company runs a popular online retail platform that lets individual retailers sell their products to millions of customers around the world. Your company places a high value in delivering web requests with low latency, and customers have found this to be a key selling feature of the online platform. However, a recent surge in customers buying gifts for Thanks giving has seen product pages load slower than usual. Your manager has suggested using a fronting reverse proxy layer to cache images. Your performance testing lead has estimated requiring 30 GB in-memory cache for caching images of the most popular products in the sale.The reverse proxy also requires approximately 2 GB memory for various other processes and no CPU at all. How should you design this system?__[REVISAR]__

    * A. Run Redis on a single Google Compute Engine instance of type n1-standard-1, and configure Redis to use 32GB SSD persistent disk as caching backend.
    * B. Create a Kubernetes deployment from Redis image and run it in a GKE Cluster on a node pool with a single n1-standard-32 instance.
    * C. Set up Redis on a custom compute engine instance with 32 GB RAM and 6 virtual CPUs.
    * D. **Use Cloud Memorystore for Redis instance replicated across two zones and configured for 32 GB in-memory cache.**

31. Your company migrated its data warehousing solution from its on-premises data centre to Google Cloud 3 years ago. Since then, several teams have worked on diferent data warehousing and analytics needs, and have created numerous BigQuery datasets. The compliance manager is concerned at the possibility of PII data being present in these datasets and has asked you to identify all datasets that contain us_social_security_number column. How can you most eficiently identify all datasets that contain us_social_security_number column?

    * A. Write a custom script that uses bq commands to loop through all data sets and identify those containing us_social_security_number column.
    * B. **Write a custom script that queries BigQuery INFORMATION_SCHEMA.TABLE_SCHEMA where COLUMN_NAME=us_social_security_number**
    * C. Enable a Cloud Dataflow job that queries BigQuery INFORMATION_SCHEMA.TABLE_SCHEMA where COLUMN_NAME=us_social_security_number.
    * D. Search for us_social_security_number in Data Catalog.

32. You developed a new order tracking application and created a test environment in your GCP project. The order tracking system uses Google Compute engine to serve requests and relies on Cloud SQL to persist order data. Unit testing and user acceptance testing has succeeded, and you want to deploy the production environment. You want to do this while ensuring there are no routes between the test environment and the production environment. You want to follow Google recommended practices. How should you do this?

    * A. Reuse an existing production GCP project of a diferent department for deploying the production resources.
    * B. Set up a shared VPC between test GCP project and production GCP project, and configure both test and production resources to use the shared VPC to achieve maximum isolation.
    * C. Deploy the production resources in a new subnet within the existing GCP project.
    * D. **In a new GCP project, enable the required GCP services and APIs, and deploy the necessary production resources.**

33. The procurement department at your company is migration all their applications to Google Cloud, and one of their engineers have asked you to provide them IAM access to create and manage service accounts in all Cloud Projects. What should you do?

    * A. **Grant the user roles/iam.serviceAccountAdmin IAM role.**
    * B. Grant the user roles/iam.serviceAccountUser IAM role.
    * C. Grant the user roles/iam.securityAdmin IAM role.
    * D. Grant the user roles/iam.roleAdmin IAM role.

34. Your company’s backup strategy involves creating snapshots for all VMs at midnight every day. You want to write a script to retrieve a list of compute engine instances in all development and production projects and feed it to the backup script for snapshotting. What should you do?

    * A. Have your operations engineer export this information from GCP console to Cloud Datastore every day just before midnight.
    * B. Use gsutil to set up two gcloud configurations – one for each project. Write a script to activate the development gcloud configuration, retrieve the list of compute engine instances, then activate production gcloud configuration and retrieve the list of compute engine instances. Schedule the script using cron.
    * C. **Use gcloud to set up two gcloud configurations – one for each project. Write a script to activate the development gcloud configuration, retrieve the list of compute engine instances, then activate production gcloud configuration and retrieve the list of compute engine instances. Schedule the script using cron.**
    * D. Have your operations engineer execute a script in Cloud Shell to export this information to Cloud Storage every day just before midnight.

35. To prevent accidental security breaches, the security team at your company has enabled Domain Restricted Sharing to limit resource sharing in your GCP organization to just your cloud identity domain. The compliance department has engaged an external auditor to carry out the annual audit, and the auditor requires read access to all resources in the production project to follout specific sections in the audit report. How can you enable this access?

    * A. Grant the auditors’ Google account roles/viewer IAM role on the production project.
    * B. Create a new Cloud Identity account for the auditor and grant them roles/iam.securityReviewer IAM role on the production project.
    * C. **Create a new Cloud Identity account for the auditor and grant them roles/viewer IAM role on the production project.**
    * D. Grant the auditors’ Google account roles/iam.securityReviewer IAM role on the production project.

36. Your company has chosen Okta, a third-party SSO identity provider, for all its IAM requirements because of the rich feature set it offers – support for over 6,500 pre-integrated apps for SSO and over 1,000 SAML integrations. How can your company users in Cloud Identity authenticate using Okta before accessing resources in your GCP project?__[REVISAR]__

    * A. Enable OAuth 2.0 with Okta OAuth Authorization Server for desktop and mobile applications.
    * B. Update the SAML integrations on the existing third-party apps to use Google as the Identity Provider (IdP)
    * C. Enable OAuth 2.0 with Okta OAuth Authorization Server for web applications.
    * D. **Configure a SAML SSO integration with Okta as the Identity Provider (IdP) and Google as the Service Provider (SP).**

37. You have developed a containerized application that performs video classification and recognition using Video AI, and you plan to deploy this application to the production GKE cluster. You want your customers to access this application on a single public IP address on HTTPS protocol. What should you do?

    * A. **Configure a NodePort service for the application and use an Ingress service to open it to the public.**
    * B. Configure a NodePort service on port 443 for the application and set up a dynamic pool of DNS A records on the application DNS to achieve round-robin load balancing.
    * C. Configure a ClusterlP service for the application and set up a DNS A record on the application DNS to point to the IP service.
    * D. Configure an HA Proxy service for the application and set up a DNS A records on the application DNS to the public IP address of the node that runs HA Proxy.

38. Your company wants to move all its on-premises applications to Google Cloud. Most applications depend on Kubernetes orchestration, and you have chosen to deploy these applications in Google Kubernetes Engine (GKE). The security team have requested you to store all container images in a Google Container Registry (GCR) in a separate project which has an automated vulnerability management scanning set up by a security partner organization. You want to ensure the GKE cluster running in your project can download the container images from the central GCR repo in the other project. How should you do this?

    * A. **Grant the Storage Object Viewer IAM role on the GCR Repo project to the service account used by GKE nodes in your project.**
    * B. Update ACLs on each container image to provide read-only access to the service account used by GKE nodes in your project.
    * C. Enable full access to all Google APIs under Access Scopes when provisioning the GKE cluster.
    * D. In the central GCR repo project, grant the Storage Object Viewer role on the Cloud Storage bucket that contains the container images to a service account and generate a P12 key for this service account. Configure the Kubernetes service account to use this key for imagePullSecrets.

39. Your compliance ofecer has requested you to provide an external auditor view, but not edit, access to all project resources. What should you do?

    * A. Add the auditors’ account to a custom IAM role that has view-only permissions on all the project services.
    * B. Add the auditors’ account to a custom IAM role that has view-only permissions on all the project resources.
    * C. Add the auditors’ account to the predefined service viewer IAM role.
    * D. **Add the auditors’ account to the predefined project viewer IAM role.**

4. Your company has a requirement to persist logs from all compute engine instances in a single BigQuery dataset called pt-logs. Your colleague ran a script to install Cloud logging agent on all the VMs, but the logs from the VMs haven’t made their way to the BigQuery dataset. What should you do to fix this issue?

    * A. Configure a job in BigQuery to fetch all Compute Engine logs from Stackdriver. Set up Cloud Scheduler to trigger a Cloud Function every day at midnight. Grant the Cloud Function the BigQuery job User role on the pt-logs dataset and trigger the BigQuery job from Cloud Function.
    * B. Create an export for all logs in Cloud Logging and set up a Cloud Pub/Sub topic as the sink destination. Have a Cloud Function trigger based on the messages in the topic and configure it to send logs Compute Engine service to BigQuery pt-logs dataset.
    * C. **Create an export for Compute Engine logs in Cloud Logging and set up BigQuery pt-logs dataset as sink destination.**
    * D. Add a metadata tag with key: logs-destination and value: bq://pt-logs, and grant the VMservice accounts BigQuery Data Editor role on the pt-logs dataset.

40. Your company is migrating its on-premises data centre to Google Cloud Platform in several phases. The current phase requires the migration of the LDAP server onto a Compute Engine instance. However, several legacy applications in your on-premises data centre and few third-party applications still depend on the LDAP server for user authentication. How can you ensure the LDAP server is publicly reachable via TLS on UDP port 636?__[REVISAR]__

    * A. **Configure a firewall rule to allow inbound (ingress) UDP traffic on port 636 from 0.0.0.0/0 for the network tag allow-inbound-udp-636, and add this network tag to the LDAP server Compute Engine Instance.**
    * B. Configure a firewall rule to allow outbound (egress) UDP traffic on port 636 to 0.0.0.0/0 for the network tag allow-outbound-udp-636, and add this network tag to the LDAP server Compute Engine Instance.
    * C. Add default-allow-udp network tag to the LDAP server Compute Engine Instance.
    * D. Configure a firewall route called default-allow-udp and have the next hop as the LDAP server Compute Engine Instance.

41. The compliance manager asked you to provide an external auditor with a report of when Cloud Identity users in your company were granted IAM roles for Cloud Spanner. How should you retrieve this information?

    * A. Retrieve the details from the policies section in the IAM console by filtering for Cloud Spanner IAM roles.
    * B. Retrieve the information from Cloud Monitoring console by filtering data logs for Cloud Spanner IAM roles.
    * C. **Retrieve the information from Cloud Logging console by filtering admin activity logs for Cloud Spanner IAM roles.**
    * D. Retrieve the details from Cloud Spanner console.

42. Your company has three GCP projects – development, test and production – that are all linked to the same billing account. Your finance department has asked you to set up an alert to notify the testing team when the Google Compute Engine service costs in the test project exceed a threshold. How should you do this?__[REVISAR]__

    * A. Ask your finance department to grant you the Project Billing Manager IAM role. Set up a budget and an alert in the billing account.
    * B. Ask your finance department to grant you the Project Billing Manager IAM role. Set up a budget and an alert for the test project in the billing account.
    * C. Ask your finance department to grant you the Billing Account Administrator IAM role. Setup a budget and an alert in the billing account. Ask your finance department to grant you the Billing Account
    * D. **Administrator IAM role. Set up a budget and an alert for the test project in the billing account.**

43. Your company has a Citrix Licensing Server in a Windows VM in your on-premises data centre and needs to migrate this to Google Cloud Platform. You have provisioned a new Windows VM in a brand new Google project, and you want to RDP to the instance to install and register the licensing server. What should you do?__[REVISAR]__

    * A. Generate a JSON key for the default GCE service account and RDP with this key.
    * B. Add a metadata tag to the instance with key: windows-password and password as thevalue, and RDP with these details.
    * C. RDP to the VM with your Google Account.
    * D. **Retrieve the RDP credentials by executing gcloud compute reset- windows-password and RDP with the credentials.**

44. Your analysts’ team needs to run a BigQuery job to retrieve customer PII data. Security policies prohibit using Cloud Shell for retrieving with PII data. The security team has advised you to set up a Shielded VM with just the required IAM access permissions to run BigQuery jobs on the specific dataset. What is the most eficient way to let the analysts SSH to the VM?__[REVISAR]__

    * A. Block project-wide public SSH keys from the instance to restrict SSH only through instance-level keys. Use ssh-keygen to generate a key for each analyst, distribute the keys to the analysts and ask them to SSH to the instance with their key from putty.
    * B. Block project-wide public SSH keys from the instance to restrict SSH only through instance-level keys. Use ssh-keygen to generate a single key for all analysts, distribute the key to the analysts and ask them to SSH to the instance with the key from putty.
    * C. Enable os Login by adding a metadata tag to the instance with key: enable- oslogin and value: TRUE. Ask the analysts to SSH to the instance through Cloud Shell.
    * D. **Enable os Login by adding a metadata tag to the instance with key: enable-oslogin and value: TRUE, and grant roles/compute.osLogin role to the analysts’ group. Ask the analysts to SSH to the instance through Cloud Shell.**

45. You want to identify a cost-eficient storage class for archival of audit logs in Google Cloud Storage. Some of these audit logs may need to be retrieved during the quarterly audit. What Storage Class should you use to minimize costs?

    * A. Nearline Storage Class.
    * B. Disaster Recovery Storage Class.
    * C. **Coldline Storage Class.**
    * D. Regional Storage Class.

46. Your production Compute workloads are running in a small subnet with a net mask 225.225.225.224. A recent surge in trafic has seen the production VMs struggle, but there are no free IP addresses for the Managed Instances Group (MIG) to autoscale. You anticipate requiring 30 additional IP addresses for the new VMs. All VMs within the subnet need to communicate with each other, and you want to do this without adding additional routes. What should you do?

    * A. Create a new subnet with a bigger non-overlapping range. Move all instances to the new subnet and delete the old subnet.
    * B. **Expand the subnet IP range.**
    * C. Create a new project and a new VPC. Share the new VPC with the existing project and configure all existing resources to use the new VPC.
    * D. Create a new subnet with a bigger overlapping range to automatically move all instances to the new subnet. Then, delete the old subnet.

47. Your runs several applications on the production GKE cluster. The machine learning team runs their training models in the default GKE cluster node pool, but the processing is slower and is delaying their analysis. You want the ML jobs to run on NVIDIA® Tesla R K80: nvidia-tesla-k80GPU for better performance and increased through put. What should you do?

    * A. **Create a new GPU enabled node pool with the required specification, and configure node selector on the pods with key: cloud.google.com/gke-accelerator and value: nvidia-tesla-k80.**
    * B. Create a dedicated GKE cluster with GPU enabled node pool as per the required specifications, and migrate the ML jobs to the new cluster.
    * C. Add a metadata tag to the pod specification with key: accelerator and value: tesla-gpu.
    * D. Terminate all existing nodes in the node pools and create new nodes with the required GPUs attached.

48. You work for a multinational conglomerate that has thousands of GCP projects and a very complex resource hierarchy that includes over 100 folders. An external audit team has requested to view this hierarchy to fill out sections of a report. You want to enable them to view the hierarchy while ensuring they can’t do anything else. What should you do?__[REVISAR]__

    * A. Grant all individual auditors roles/browser IAM role.
    * B. Add all individual auditors to an IAM group and grant the group roles/iam.roleViewerIAM role.
    * C. **Add all individual auditors to an IAM group and grant the group roles/browser IAM role.**
    * D. Grant all individual auditors roles/iam.roleViewer IAM role.

49. EU GDPR requires you to archive all customer PII data indefinitely. The compliance department needs access to this data during the annual audit and is happy for the data to be archived after 30 days to save on storage costs. You want to design a cost-eficient solution for storing this data. What should you do?__[REVISAR]__

    * A. **Store new data in Regional Storage Class, and add a lifecycle rule to transition data older than 30 days to Coldline Storage Class.**
    * B. Store new data in Regional Storage Class, and add a lifecycle rule to transition data older than 30 days to Nearline Storage Class.
    * C. Store new data in Multi-Regional Storage Class, and add a lifecycle rule to transition data older than 30 days to Nearline Storage Class.
    * D. Store new data in Multi-Regional Storage Class, and add a lifecycle rule to transition data older than 30 days to Coldline Storage Class.

5. Your finance department has asked you to provide their team access to view billing reports for all GCP projects. What should you do?

    * A. Grant roles/billing.User IAM role to the 􀃕nance group.
    * B. Grant roles/billing.ProjectManager IAM role to the 􀃕nance group.
    * C. Grant roles/billing.Admin IAM role to the 􀃕nance group.
    * D. **Grant roles/billing. Viewer IAM role to the 􀃕nance group.**

50. You have developed an enhancement for a photo compression application running on the App Engine Standard service in Google Cloud Platform, and you want to canary test this enhancement on a small percentage of live users before completely switching of the old version. How can you do this?__[REVISAR]__

    * A. Deploy the enhancement in a GKE cluster and enable traffic splitting in GCP console.
    * B. **Deploy the enhancement as a new version of the application and enable traffc splitting in GCP console.**
    * C. Deploy the enhancement in a GCE VM and enable traffic splitting in GCP console.
    * D. Deploy the enhancement as a new application in App Engine Standard and enable traffic splitting in GCP console.

6. Your company processes gigabytes of image thumbnails every day and stores them in your on-premises data centre. Your team developed an application that uses these image thumbnails with GCP services such as Auto ML vision and pre-trained Vision API models to detect emotion, understand text and much more. The Cloud Security team has created a service account with the appropriate level of access; however, your team is unaware of how to authenticate to the GCP Services and APIs using the service account. What should you do?

    * A. **Run gcloud iam service-accounts keys create to generate a JSON key file for the service account and configure your on-premises application to present the JSON key file.**
    * B. Configure your on-premises application to use the service account username and password credentials.
    * C. Create an IAM user with the appropriate permissions and use the username and password in your on-premises application.
    * D. Configure the Direct interconnect to authenticate requests from your on-premises network automatically.

7. A Data Support Engineer at your company accidentally disclosed customer PII data in a support case in Google Cloud Console. Your compliance team wants to prevent this from occurring again and has asked you to set them up as approvers for cases raised by support teams. You want to follow Google Best Practices. What IAM access should you grant them?__[REVISAR]__

    * A. Grant roles/iam.roleAdmin IAM role to the compliance team group.
    * B. **Grant roles/accessapprovalapprover IAM role to the compliance team group.**
    * C. Grant roles/iam.roleAdmin IAM role to all members of the compliance team.
    * D. Grant roles/accessapprovalapprover IAM role to all members of the compliance team.

8. You created a deployment manager template to automate the provisioning of a production Google Kubernetes Engine (GKE) cluster. The GKE cluster requires a monitoring pod running on each node (DaemonSet) in daemon-system namespace, and your manager has asked you to identify if it is possible to automate the provisioning of the monitoring pod along with the cluster using the least number of resources. How should you do this?

    * A. Update the deployment manager template to add a metadata tag with key: daemon-system and value: DaemonSet manifest YAML.
    * B. Have the Runtime Configurator create a Runtime Config resource with the DaemonSet definition.
    * C. **Add a new type provider in Deployment Manager for Kubernetes APIs and use the new type provider to create the DaemonSet resource.**
    * D. Update the deployment manager template to provision a preemptable compute engine instance and configure its startup script to use kubectl to create the DaemonSet.

9. Your company has two GCP organizations – one for development (and test) resources, and another for production resources. Each GCP organization has a billing account and several GCP projects. The new CFO doesn’t like this billing structure and has asked your team to consolidate costs from all GCP projects onto a single invoice as soon as possible. What should you do?__[REVISAR]__

    * A. Move all the projects from production GCP organization into development GCP organization and link them to the development billing account.
    * B. Move all projects from both organizations into a new GCP organization and link all the projects to a new billing account in the new GCP organization.
    * C. **Link all projects from production GCP organization to the billing account used by development GCP organization.**
    * D. Have both the billing account export their billing data to a single BigQuery dataset.

MALAS:22