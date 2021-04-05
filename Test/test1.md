# Google Associate Cloud Engineer Practice 
# Exam Part - 7

1. Your company stores terabytes of image thumbnails in Google Cloud Storage bucket withversioning enabled. An engineer deleted a current (live) version of an image and a non-current(not live) version of another image. What is the outcome of this operation?

    * A. The deleted current version becomes a non-current version, and a lifecycle rule isapplied to delete after 30 days. A lifecycle rule is applied on the deleted non-current versionto delete after 30 days.
    * B. The deleted current version becomes a non-current version, and a lifecycle rule isapplied to transition to Nearline Storage after 30 days. A lifecycle rule is applied on thedeleted non-current version to transition to Nearline Storage after 30 days.
    * C. The deleted current version is deleted permanently. The deleted non-current version isdeleted permanently.
    * D. The deleted current version becomes a non-current version. The deleted non-currentversion is deleted permanently.

10. Your company has terabytes of audit logs and analytics data in multiple BigQuery datasets.Some of these data sets need to be retained long term for audit purposes. You want to ensureanalysts do not delete this data. What should you do?

    * A. Grant a custom role with just the required query permissions to all the analysts.
    * B. Grant ples/bigquery.dataOwner IAM role to the analysts’ group.
    * C. Grant roles/bigquery.user IAM role to the analysts’ group.
    * D. Grant a custom role with just the required query permissions to the analysts’ group.

11. You developed a new mobile game that uses Cloud Spanner for storing user state, playerpro􀃕le and leaderboard. Data is always accessed by using the primary key. Your performancetesting team identi􀃕ed latency issues in the application, and you suspect it might be related totable primary key con􀃕guration. You created the table by executing this DDL:

1. CREATE TABLE users {
user_id INT64 NOT NULL,
user_name STRING (255),
email_address STRING (255)
} PRIMARY KEY (user_id)

What should you do to 􀃕x this read latency issue?

    * A. Add another index on user_id column to speed up the data retrieval.
    * B. Make the table smaller by removing email_address and add another index on user_idcolumn to speed up the data retrieval.
    * C. Make the table smaller by removing email_address.
    * D. Update the primary key (user_id) to not have sequential values.

12. There has been an increased phishing email activity recently, and you deployed a newapplication on a GKE cluster to help scan and detect viruses in uploaded 􀃕les. Each time theFinance or HR department receive an email with an attachment, they use this application to scanthe email attachment for viruses. The application pods open the email attachment in asandboxed environment before initiating a virus scan. Some infected email attachments may runarbitrary phishing code with elevated privileges in the container. You want to ensure that thepods that run these scans do not impact pods of other applications running in the same GKEcluster. How can you achieve this isolation between pods?

    * A. Detect vulnerabilities in the application container images in GCR repo by using theContainer Analysis API.
    * B. Create a new (non-default) node pool with sandbox type set to gvisor and con􀃕gure thedeployment spec with a runtimeClassName of gvisor.
    * C. Con􀃕gure the pods to use containerd as the runtime by adding a node selector with key:cloud.google.com/gke-os-distribution and value:cos_containerd.
    * D. Have your applications use trusted container images by enabling Binary Authorization.

13. An external partner working on a production issue has asked you to share a list of all GCP APIsenabled for your GCP production project – production_v1. How should you retrieve thisinformation?

    * A. Execute gcloud services list – -available to retrieve a list of all services enabled for theproject.
    * B. Execute gcloud projects list –􀃕lter=’name:production_vl’ to retrieve the ID of the project,and execute gcloud services list –project to retrieve a list of all services enabled for theproject.
    * C. Execute gcloud init production_v1 to set production_v1 as the current project in gcloudcon􀃕guration and execute gcloud services list -available to retrieve a list of all servicesenabled for the project.
    * D. Execute gcloud info to retrieve the account information and execute gcloud services list –-account to retrieve a list of all services enabled for the project.

14. Your 􀃕nance team owns two GCP projects – one project for payroll applications and anotherproject for accounts. You need the VMs in the payroll project in one VPC to communicate withVMs in accounts project in a di􀃠erent VPC and vice versa. How should you do it?

    * A. Ensure you have the Administrator role on both projects and move all instances to twonew VPCs.
    * B. Share the VPC from one of the projects and have the VMs in the other project use theshared VPC. Ensure both projects belong to the same GCP organization.
    * C. Create a new VPC and move all VMs to the new VPC. Ensure both projects belong to thesame GCP organization.
    * D. Ensure you have the Administrator role on both projects and move all instances to asingle new VPC.

15. Your company procured a license for a third-party cloud-based document signing system forthe procurement team. All members of the procurement team need to sign in with the sameservice account. Your security team prohibits sharing service account passwords. You have beenasked to recommend a solution that lets the procurement team login as the service account inthe document signing system but without the team knowing the service account password. Whatshould you do?

    * A. Have a single person from the procurement team access the document signing systemwith the service account credentials.
    * B. Register the application as a password vaulted app and set the credentials to the serviceaccount credentials.
    * C. Ask the third-party provider to enable OAuth 2.0 for the application and set the
    * D. Ask the third-party provider to enable SAML for the application and set the credentials tothe service account credentials.

16. Your company uses a legacy application that still relies on the legacy LDAP protocol toauthenticate. Your company plans to migrate this application to the cloud and is looking for acost-e􀃠ective solution while minimizing any developer e􀃠ort. What should you do?

    * A. Modify the legacy application to use SAML and ask users to sign in through Gmail.
    * B. Modify the legacy application to use OAuth 2.0 and ask users to sign in through Gmail.
    * C. Synchronize data within your LDAP server with Google Cloud Directory Sync.
    * D. Use secure LDAP to authenticate the legacy application and ask users to sign in throughGmail.

17. You developed a python application that exposes an HTTP(s) endpoint for retrieving 2-weekweather forecast for a given location. You deployed the application in a single Google CloudCompute Engine Virtual Machine, but the application is not as popular as you anticipated and hasbeen receiving very few requests. To minimize costs, your colleague suggested containerizing theapplication and deploying on a suitable GCP compute service. Where should you deploy yourcontainers?

    * A. App Engine Flexible.
    * B. GKE with horizontal pod autoscaling and cluster autoscaler enabled.
    * C. Cloud Run.
    * D. Cloud Run on GKE.

18. You developed a python application that gets triggered by messages from a Cloud Pub/Subtopic. Your manager is a big fan of both serverless and containers and has asked you tocontainerize the application and deploy on Google Cloud Run. How should you do it?

    * A. Assign roles/pubsub.subscribei role (Pub/Sub Subscriber role) to the Cloud Run serviceaccount. Set up a Cloud Pub/Sub subscription on the topic and con􀃕gure the application topull messages.
    * B. Deploy your application to Google Cloud Run on GKE. Set up a Cloud Pub/Subsubscription on the topic and deploy a sidecar container in the same GKE cluster toconsume the message from the topic and push it to your application.
    * C. Assign roles/run.invoker role (Cloud Run Invoker role) on your Cloud Run application to aservice account. Set up a Cloud Pub/Sub subscription on the topic and con􀃕gure it to use
    * D. Trigger a Cloud Function whenever the topic receives a new message. From the CloudFunction, invoke Cloud Run.

19. Your data warehousing team executed an Apache Sqoop job to export data from Hive/Hbaseand uploaded this data in AVRO 􀃕le format to Cloud Storage. The business analysts at yourcompany have years of experience using SQL. They have asked you to identify if there is a cost-e􀃠ective way to query the information in AVRO 􀃕les through SQL. What should you do?

    * A. Transfer the data from Cloud Storage to BigQuery and advise the business analysts torun their SQL queries in BigQuery.
    * B. Transfer the data from Cloud Storage to HDFS. Con􀃕gure an external table in Hive topoint to HDFS and advise the business analysts to run their SQL queries in Hive.
    * C. Point a BigQuery external table at the Cloud Storage bucket and advise the businessanalysts to run their SQL queries in BigQuery.
    * D. Transfer the data from Cloud Storage to Cloud Datastore and advise the businessanalysts to run their SQL queries in Cloud Datastore.

2. Your company wants to move all its on-premises applications to Google Cloud. Mostapplications depend on Kubernetes orchestration, and you have chosen to deploy theseapplications in Google Kubernetes Engine (GKE) in your GCP project app_prod. The security teamhave requested you to store all container images in Google Container Registry (GCR) in a separateproject gcr_ proj, which has an automated vulnerability management scanning set up by asecurity partner. You are ready to push an image to GCR repo and want to tag it as tranquillity:v1.How should you do it?

    * A. Execute gcloud builds submit –tag gcr.io/gcr_proj/tranquillity from Cloud shell.
    * B. Execute gcloud builds submit –tag gcr.io/app_prod/tranquillity:v1 from Cloud shell.
    * C. Execute gcloud builds submit –tag gcr.io/app_prod/tranquillity from Cloud shell.
    * D. Execute gcloud builds submit –tag gcr.io/gcr_proj/tranquillity:v1 from Cloud shell.

20. Your company has several business-critical applications running on its on-premises datacentre, which is already at full capacity, and you need to expand to Google Cloud Platform tohandle tra􀃞c bursts. You want to virtual machine instances in both on-premises data centre andGoogle Cloud Compute Engine to communicate via their internal IP addresses. What should youdo?

    * A. Add bastion hosts in GCP as well as on-premises network and set up a proxy tunnelbetween the bastion hosts in GCP and the bastion hosts in the on-premises network. Allowapplications in the data centre to scale to Google Cloud through the proxy tunnel.
    * B. Create a new GCP project and a new VPC and enable VPC peering between the new VPCand networks in the data centre.
    * C. Create a new VPC in GCP with a non-overlapping IP range and con􀃕gure Cloud VPNbetween the on-premises network and GCP.
    * D. Allow applications in the data centre to scale to Google Cloud through the VPN tunnel.
    * E. Create a new GCP project and a new VPC and make this a shared VPC with the on-premises network. Allow applications in the data centre to scale to Google Cloud on theshared VPC.

21. The machine learning team at your company infrequently needs to use a GKE cluster withspeci􀃕c GPUs for processing a non-restartable and long-running job. How should you set up theGKE cluster for this requirement?

    * A. Deploy the workload on a node pool with non-preemptible compute engine instancesand GPUs attached to them. Enable cluster autoscaling and set min-nodes to 1.
    * B. Deploy the workload on a node pool with preemptible compute engine instances andGPUs attached to them.
    * C. Enable GKE cluster node auto-provisioning.
    * D. Enable Vertical Pod Autoscaling.

22. You want to deploy an application to GKE cluster to enable the translation of mp3 􀃕les. Theapplication uses an opensource translation library that is IOPS intensive. The organization backupstrategy involves taking disk snapshots of all nodes at midnight. You want to estimate the cost ofrunning this application in GKE cluster for the next month. In addition to the node pool size,instance type, location and usage duration, what else should you 􀃕ll in the GCP pricing calculatorwhen estimating the cost of running this application?

    * A. GPU and GKE Cluster Management Fee.
    * B. Local SSD, Snapshot Storage and Persistent disk storage.
    * C. GPU, Snapshot Storage and Persistent disk storage.
    * D. Local SSD and GKE Cluster Management Fee.

23. Your organization has several applications in the on-premises data centre that depend onActive Directory for user identi􀃕cation and authorization. Your organization is planning amigration to Google Cloud Platform and requires complete control over the Cloud Identity
accounts used by sta􀃠 to access Google Services and APIs. Where possible, you want to re-useActive Directory as the source of truth for identi􀃕cation and authorization. What should you do?

    * A. Ask all sta􀃠 to create Cloud Identity accounts using their Google email address andrequire them to re-use their AD password for Cloud Identity account.
    * B. Create a custom script that synchronizes identities between Active Directory and CloudIdentity. Use Google Cloud Scheduler to run the script regularly.
    * C. Ask your operations team to export identities from active directory into a comma-separated 􀃕le and use GCP console to import them into Cloud Identity daily.
    * D. Synchronize users in Google Cloud Identity with identities in Active directory by runningGoogle Cloud Directory Sync (GCDS).

24. Your colleague is learning about docker images, containers and Kubernetes, and has recentlydeployed a sample application to a GKE You deployed a demo application on a GKE cluster thatuses preemptible nodes. The deployment has 2 replicas, and although the demo application isresponding to requests, the output from Cloud Shell shows one of the pods is pending state.1
kubectl get pods -1 app=demo
What is the most likely explanation for this behaviour?

    * A. The pod in the pending state is unable to download the docker image.
    * B. The node got preempted before the pod could be started fully. GKE cluster master isprovisioning a new node.
    * C. The pod in the pending state is too big to 􀃕t on a single preemptible VM. The node poolneeds to be recreated with a bigger machine type.
    * D. Cluster autoscaling is not enabled, and the existing (only) node doesn’t have enoughresources for provisioning the pod.

25. Your company stores terabytes of image thumbnails in Google Cloud Storage bucket withversioning enabled. You want to cut down the storage costs and you spoke to the image editinglab to understand their usage requirements. They inform you that they access noncurrentversions of images at most once a month and are happy for you to archive these objects after 30days from the date of creation, however, there may be a need to retrieve and update some ofthese archived objects at the end of each month. What should you do?

    * A. Con􀃕gure a lifecycle rule to transition non-current versions to Coldline Storage Classafter 30 days.
    * B. Con􀃕gure a lifecycle rule to transition objects from Regional Storage Class to ColdlineStorage Class after 30 days.
    * C. Con􀃕gure a lifecycle rule to transition objects from Regional Storage Class to Nearline
Storage Class after 30 days.
    * D. Con􀃕gure a lifecycle rule to transition non-current versions to Nearline Storage Classafter 30 days.

26. A mission-critical image processing application running in your on-premises data centrerequires 64 virtual CPUs to execute all processes. You colleague wants to migrate this mission-critical application to Google Cloud Platform Compute Engine and has asked your suggestion forthe instance size. What should you suggest?

    * A. Provision the compute engine instance on the default settings, then modify it to have 64vCPUs.
    * B. Provision the compute engine instance on the default settings, then scale it as per sizingrecommendations.
    * C. Use n1-standard-64 machine type when provisioning the compute engine instance.
    * D. Use Xeon Scalable Processor (Skylake) as the CPU platform when provisioning thecompute engine instance.

27. Your company has accumulated terabytes of analytics data from clickstream logsand storesthis data in BigQuery dataset in a central GCP project. Analytics teams from several departmentsin multiple GCP projects run queries against this data. The costs for BigQuery job executions haveincreased drastically in recent months, and your 􀃕nance team has asked your suggestions forcontrolling these spiralling costs. What should you do? (Select two)

    * A. Separate the data of each department and store it in BigQuery in their GCPproject.Enable BigQuery quota on a per-project basis.
    * B. Create a separate GCP project for each department and con􀃕gure billing settings oneach project to pick up the costs for queries ran by their analytics team.
    * C. Move to BigQuery 􀃖at rate and purchase the required number of query slots.
    * D. Replicate the data in all GCP projects & have each department query data from their GCPproject instead of the central BigQuery project.

28. All development teams at your company share the same development GCP project,and thishas previously resulted in some teams accidentally terminating compute engine resources ofother teams, causing downtime and loss of productivity. You want to deploy a new application tothe shared development GCP project, and you want to protect your instance from such issues.What should you do?

    * A. Deploy the application on a Preemptible VM.
    * B. Set the deletionProtection property on the VM.
    * C. Deploy the application on a Shielded VM.
    * D. Deploy the application on VMs provisioned on sole-tenant nodes.

29. You want to provide an operations engineer access to a speci􀃕c GCP project. Everyone at yourcompany has G Suite accounts. How should you grant access?

    * A. Run G Suite to Cloud Identity migration tool to convert G Suite Accounts intoCloudIdentity accounts. Grant the necessary roles to the Cloud Identity account.
    * B. Add the operations engineer to the gcp-console-access group in your G Suite domainand grant the necessary roles to the group.
    * C. Assign the necessary roles to their G Suite email address.
    * D. Disable G Suite Sign in, enable Cloud Identity Sign in, and add their email address toCloud Identity. Grant the necessary roles to the Cloud Identity account.

3. Your company runs a popular online retail platform that lets individual retailers sell theirproducts to millions of customers around the world. Your company places a high value indelivering web requests with low latency, and customers have found this to be a key sellingfeature of the online platform. However, a recent surge in customers buying gifts forThanksgiving has seen product pages load slower than usual. Your manager has suggested usinga fronting reverse proxy layer to cache images. Your performance testing lead has estimatedrequiring 30 GB in-memory cache for caching images of the most popular products in the sale.The reverse proxy also requires approximately 2 GB memory for various other processes and noCPU at all. How should you design this system?

    * A. Run Redis on a single Google Compute Engine instance of type n1-standard-1, andcon􀃕gure Redis to use 32GB SSD persistent disk as caching backend.
    * B. Create a Kubernetes deployment from Redis image and run it in a GKE Cluster on a nodepool with a single n1-standard-32 instance.
    * C. Set up Redis on a custom compute engine instance with 32 GB RAM and 6 virtual CPUs.
    * D. Use Cloud Memorystore for Redis instance replicated across two zones and con􀃕guredfor 32 GB in-memory cache.

31. Your company migrated its data warehousing solution from its on-premises data centre toGoogle Cloud 3 years ago. Since then, several teams have worked on di􀃠erent data warehousingand analytics needs, and have created numerous BigQuery datasets. The compliance manager is
concerned at the possibility of PII data being present in these datasets and has asked you toidentify all datasets that contain us_social_security_number column. How can you most e􀃞cientlyidentify all datasets that contain us_social_security_numbercolumn?

    * A. Write a custom script that uses bq commands to loop through all data sets and identifythose containing us_social_security_number column.
    * B. Write a custom script that queries BigQueryINFORMATION_SCHEMA.TABLE_SCHEMAwhereCOLUMN_NAME=us_social_security_number
    * C. Enable a Cloud Data􀃖ow job that queries BigQueryFORMATION_SCHEMA.TABLE_SCHEMA where COLUMN_NAME=us_socialsecurity_number.
    * D. Search for us_social_security_number in Data Catalog.

32. You developed a new order tracking application and created a test environment in your GCPproject. The order tracking system uses Google Compute engine to serve requests and relies onCloud SQL to persist order data. Unit testing and user acceptance testing has succeeded, and youwant to deploy the production environment. You want to do this while ensuring there are noroutes between the test environment and the production environment. You want to followGoogle recommended practices. How should you do this?

    * A. Reuse an existing production GCP project of a di􀃠erent department for deploying theproduction resources.
    * B. Set up a shared VPC between test GCP project and production GCP project, andcon􀃕gure both test and production resources to use the shared VPC to achieve maximumisolation.
    * C. Deploy the production resources in a new subnet within the existing GCP project.
    * D. In a new GCP project, enable the required GCP services and APIs, and deploy thenecessary production resources.

33. The procurement department at your company is migration all their applications to GoogleCloud, and one of their engineers have asked you to provide them IAM access to create andmanage service accounts in all Cloud Projects. What should you do?

    * A. Grant the user roles/iam.serviceAccountAdmin IAM role.
    * B. Grant the user roles/iam.serviceAccountUser IAM role.
    * C. Grant the user roles/iam.securityAdmin IAM role.
    * D. Grant the user roles/iam.roleAdmin IAM role.

34. Your company’s backup strategy involves creating snapshots for all VMs at midnight everyday. You want to write a script to retrieve a list of compute engine instances in all developmentand production projects and feed it to the backup script for snapshotting. What should you do?

    * A. Have your operations engineer export this information from GCP console to CloudDatastore every day just before midnight.
    * B. Use gsutil to set up two gcloud con􀃕gurations – one for each project. Write a script toactivate the development gcloud con􀃕guration, retrieve the list of compute engineinstances, then activate production gcloud con􀃕guration and retrieve the list of computeengine instances. Schedule the script using cron.
    * C. Use gcloud to set up two gcloud con􀃕gurations – one for each project. Write a script toactivate the development gcloud con􀃕guration, retrieve the list of compute engineinstances, then activate production gcloud con􀃕guration and retrieve the list of computeengine instances. Schedule the script using cron.
    * D. Have your operations engineer execute a script in Cloud Shell to export this informationto Cloud Storage every day just before midnight.

35. To prevent accidental security breaches, the security team at your company has enabledDomain Restricted Sharing to limit resource sharing in your GCP organization to just your cloudidentity domain. The compliance department has engaged an external auditor to carry out theannual audit, and the auditor requires read access to all resources in the production project to 􀃕llout speci􀃕c sections in the audit report. How can you enable this access?

    * A. Grant the auditors’ Google account roles/viewer IAM role on the production project.
    * B. Create a new Cloud Identity account for the auditor and grant themroles/iam.securityReviewer IAM role on the production project.
    * C. Create a new Cloud Identity account for the auditor and grant them roles/viewer IAMrole on the production project.
    * D. Grant the auditors’ Google account roles/iam.securityReviewer IAM role on theproduction project.

36. Your company has chosen Okta, a third-party SSO identity provider, for all its IAMrequirements because of the rich feature set it o􀃠ers – support for over 6,500 pre-integratedapps for SSO and over 1,000 SAML integrations. How can your company users in Cloud Identityauthenticate using Okta before accessing resources in your GCP project?

    * A. Enable OAuth 2.0 with Okta OAuth Authorization Server for desktop and mobileapplications.
    * B. Update the SAML integrations on the existing third-party apps to use Google as theIdentity Provider (IdP)C. Enable OAuth 2.0 with Okta OAuth Authorization Server for web applications.
    * D. Con􀃕gure a SAML SSO integration with Okta as the Identity Provider (IdP) and Google asthe Service Provider (SP).

37. You have developed a containerized application that performs video classi􀃕cation andrecognition using Video AI, and you plan to deploy this application to the production GKE cluster.You want your customers to access this application on a single public IP address on HTTPSprotocol. What should you do?

    * A. Con􀃕gure a NodePort service for the application and use an Ingress service to open it tothe public.
    * B. Con􀃕gure a NodePort service on port 443 for the application and set up a dynamic poolof DNS A records on the application DNS to achieve round-robin load balancing.
    * C. Con􀃕gure a ClusterlP service for the application and set up a DNS A record on theapplication DNS to point to the IP service.
    * D. Con􀃕gure an HAProxy service for the application and set up a DNS A records on theapplication DNS to the public IP address of the node that runs HAProxy.

38. Your company wants to move all its on-premises applications to Google Cloud. Mostapplications depend on Kubernetes orchestration, and you have chosen to deploy theseapplications in Google Kubernetes Engine (GKE). The security team have requested you to storeall container images in a Google Container Registry (GCR) in a separate project which has anautomated vulnerability management scanning set up by a security partner organization. Youwant to ensure the GKE cluster running in your project can download the container images fromthe central GCR repo in the other project. How should you do this?

    * A. Grant the Storage Object Viewer IAM role on the GCR Repo project to the service accountused by GKE nodes in your project.
    * B. Update ACLs on each container image to provide read-only access to the service accountused by GKE nodes in your project.
    * C. Enable full access to all Google APIs under Access Scopes when provisioning the GKEcluster.
    * D. In the central GCR repo project, grant the Storage Object Viewer role on the CloudStorage bucket that contains the container images to a service account and generate a P12key for this service account. Con􀃕gure the Kubernetes service account to use this key forimagePullSecrets.

39. Your compliance o􀃞cer has requested you to provide an external auditor view, but not edit,access to all project resources. What should you do?

    * A. Add the auditors’ account to a custom IAM role that has view-only permissions on all theproject services.
    * B. Add the auditors’ account to a custom IAM role that has view-only permissions on all theproject resources.
    * C. Add the auditors’ account to the prede􀃕ned service viewer IAM role.
    * D. Add the auditors’ account to the prede􀃕ned project viewer IAM role.

4. Your company has a requirement to persist logs from all compute engine instances in a singleBigQuery dataset called pt-logs. Your colleague ran a script to install Cloud logging agent on allthe VMs, but the logs from the VMs haven’t made their way to the BigQuery dataset. What shouldyou do to 􀃕x this issue?

    * A. Con􀃕gure a job in BigQuery to fetch all Compute Engine logs from Stackdriver. Set upCloud Scheduler to trigger a Cloud Function every day at midnight. Grant the CloudFunction the BigQuery jobUser role on the pt-logs dataset and trigger the BigQuery jobfrom Cloud Function.
    * B. Create an export for all logs in Cloud Logging and set up a Cloud Pub/Sub topic as thesink destination. Have a Cloud Function trigger based on the messages in the topic andcon􀃕gure it to send logs Compute Engine service to BigQuery pt-logs dataset.
    * C. Create an export for Compute Engine logs in Cloud Logging and set up BigQuery pt-logsdataset as sink destination.
    * D. Add a metadata tag with key: logs-destination and value: bq://pt-logs, and grant the VMservice accounts BigQuery Data Editor role on the pt-logs dataset.

40. Your company is migrating its on-premises data centre to Google Cloud Platform in severalphases. The current phase requires the migration of the LDAP server onto a Compute Engineinstance. However, several legacy applications in your on-premises data centre and few third-party applications still depend on the LDAP server for user authentication. How can you ensurethe LDAP server is publicly reachable via TLS on UDP port 636?

    * A. Con􀃕gure a 􀃕rewall rule to allow inbound (ingress) UDP tra􀃞c on port 636 from 0.0.0.0/0for the network tag allow-inbound-udp-636, and add this network tag to the LDAP serverCompute Engine Instance.
    * B. Con􀃕gure a 􀃕rewall rule to allow outbound (egress) UDP tra􀃞c on port 636 to 0.0.0.0/0for the network tag allow-outbound-udp-636, and add this network tag to the LDAP serverCompute Engine Instance.
    * C. Add default-allow-udp network tag to the LDAP server Compute Engine Instance.
    * D. Con􀃕gure a 􀃕rewall route called default-allow-udp and have the next hop as the LDAPserver Compute Engine Instance.

41. The compliance manager asked you to provide an external auditor with a report of whenCloud Identity users in your company were granted IAM roles for Cloud Spanner. How should youretrieve this information?

    * A. Retrieve the details from the policies section in the IAM console by 􀃕ltering for CloudSpanner IAM roles.
    * B. Retrieve the information from Cloud Monitoring console by 􀃕ltering data logs for CloudSpanner IAM roles.
    * C. Retrieve the information from Cloud Logging console by 􀃕ltering admin activity logs forCloud Spanner IAM roles.
    * D. Retrieve the details from Cloud Spanner console.

42. Your company has three GCP projects – development, test and production – that are all linkedto the same billing account. Your 􀃕nance department has asked you to set up an alert to notifythe testing team when the Google Compute Engine service costs in the test project exceed athreshold. How should you do this?

    * A. Ask your 􀃕nance department to grant you the Project Billing Manager IAM role. Set up abudget and an alert in the billing account.
    * B. Ask your 􀃕nance department to grant you the Project Billing Manager IAM role. Set up abudget and an alert for the test project in the billing account.
    * C. Ask your 􀃕nance department to grant you the Billing Account Administrator IAM role. Setup a budget and an alert in the billing account. Ask your 􀃕nance department to grant youthe Billing Account
    * D. Administrator IAM role. Set up a budget and an alert for the test project in the billingaccount.

43. Your company has a Citrix Licensing Server in a Windows VM in your on-premises data centreand needs to migrate this to Google Cloud Platform. You have provisioned a new Windows VM ina brand new Google project, and you want to RDP to the instance to install and register thelicensing server. What should you do?

    * A. Generate a JSON key for the default GCE service account and RDP with this key.
    * B. Add a metadata tag to the instance with key: windows-password and password as thevalue, and RDP with these details.
    * C. RDP to the VM with your Google Account.
    * D. Retrieve the RDP credentials by executing gcloud compute reset- windows-password andRDP with the credentials.

44. Your analysts’ team needs to run a BigQuery job to retrieve customer PII data. Securitypolicies prohibit using Cloud Shell for retrieving with PII data. The security team has advised youto set up a Shielded VM with just the required IAM access permissions to run BigQuery jobs onthe speci􀃕c dataset. What is the most e􀃞cient way to let the analysts SSH to the VM?

    * A. Block project-wide public SSH keys from the instance to restrict SSH only throughinstance-level keys. Use ssh-keygen to generate a key for each analyst, distribute the keysto the analysts and ask them to SSH to the instance with their key from putty.
    * B. Block project-wide public SSH keys from the instance to restrict SSH only throughinstance-level keys. Use ssh-keygen to generate a single key for all analysts, distribute thekey to the analysts and ask them to SSH to the instance with the key from putty.
    * C. Enable os Login by adding a metadata tag to the instance with key: enable- oslogin andvalue: TRUE. Ask the analysts to SSH to the instance through Cloud Shell.
    * D. Enable os Login by adding a metadata tag to the instance with key: enable-oslogin andvalue: TRUE, and grant roles/compute.osLogin role to the analysts’ group. Ask the analyststo SSH to the instance through Cloud Shell.

45. You want to identify a cost-e􀃞cient storage class for archival of audit logs in Google CloudStorage. Some of these audit logs may need to be retrieved during the quarterly audit. WhatStorage Class should you use to minimize costs?

    * A. Nearline Storage Class.
    * B. Disaster Recovery Storage Class.
    * C. Coldline Storage Class.
    * D. Regional Storage Class.

46. Your production Compute workloads are running in a small subnet with a netmask225.225.225.224. A recent surge in tra􀃞c has seen the production VMs struggle, but there are nofree IP addresses for the Managed Instances Group (MIG) to autoscale. You anticipate requiring30 additional IP addresses for the new VMs. All VMs within the subnet need to communicate witheach other, and you want to do this without adding additional routes. What should you do?

    * A. Create a new subnet with a bigger non-overlapping range. Move all instances to the newsubnet and delete the old subnet.
    * B. Expand the subnet IP range.
    * C. Create a new project and a new VPC. Share the new VPC with the existing project andcon􀃕gure all existing resources to use the new VPC.
    * D. Create a new subnet with a bigger overlapping range to automatically move all instancesto the new subnet. Then, delete the old subnet.

47. Your runs several applications on the production GKE cluster. The machine learning teamruns their training models in the default GKE cluster node pool, but the processing is slower andis delaying their analysis. You want the ML jobs to run on NVIDIA® Tesla R K80: nvidia-tesla-k80GPU for better performance and increased throughput. What should you do?

    * A. Create a new GPU enabled node pool with the required speci􀃕cation, and con􀃕gure nodeselector on the pods with key: cloud.google.com/gke-accelerator and value: nvidia-tesla-k80.
    * B. Create a dedicated GKE cluster with GPU enabled node pool as per the requiredspeci􀃕cations, and migrate the ML jobs to the new cluster.
    * C. Add a metadata tag to the pod speci􀃕cation with key: accelerator and value: tesla-gpu.
    * D. Terminate all existing nodes in the node pools and create new nodes with the requiredGPUs attached.

48. You work for a multinational conglomerate that has thousands of GCP projects and a verycomplex resource hierarchy that includes over 100 folders. An external audit team has requestedto view this hierarchy to 􀃕ll out sections of a report. You want to enable them to view thehierarchy while ensuring they can’t do anything else. What should you do?

    * A. Grant all individual auditors roles/browser IAM role.
    * B. Add all individual auditors to an IAM group and grant the group roles/iam.roleViewerIAM role.
    * C. Add all individual auditors to an IAM group and grant the group roles/browser IAM role.
    * D. Grant all individual auditors roles/iam.roleViewer IAM role.

49. EU GDPR requires you to archive all customer PII data inde􀃕nitely. The compliancedepartment needs access to this data during the annual audit and is happy for the data to bearchived after 30 days to save on storage costs. You want to design a cost-e􀃞cient solution forstoring this data. What should you do?

    * A. Store new data in Regional Storage Class, and add a lifecycle rule to transition data olderthan 30 days to Coldline Storage Class.
    * B. Store new data in Regional Storage Class, and add a lifecycle rule to transition data olderthan 30 days to Nearline Storage Class.
    * C. Store new data in Multi-Regional Storage Class, and add a lifecycle rule to transition dataolder than 30 days to Nearline Storage Class.
    * D. Store new data in Multi-Regional Storage Class, and add a lifecycle rule to transition dataolder than 30 days to Coldline Storage Class.

5. Your 􀃕nance department has asked you to provide their team access to view billing reports forall GCP projects. What should you do?

    * A. Grant roles/billing.User IAM role to the 􀃕nance group.
    * B. Grant roles/billing.ProjectManager IAM role to the 􀃕nance group.
    * C. Grant roles/billing.Admin IAM role to the 􀃕nance group.
    * D. Grant roles/billing. Viewer IAM role to the 􀃕nance group.

50. You have developed an enhancement for a photo compression application running on theApp Engine Standard service in Google Cloud Platform, and you want to canary test thisenhancement on a small percentage of live users before completely switching o􀃠 the old version.How can you do this?

    * A. Deploy the enhancement in a GKE cluster and enable tra􀃞c splitting in GCP console.
    * B. Deploy the enhancement as a new version of the application and enable tra􀃞c splittingin GCP console.
    * C. Deploy the enhancement in a GCE VM and enable tra􀃞c splitting in GCP console.
    * D. Deploy the enhancement as a new application in App Engine Standard and enable tra􀃞csplitting in GCP console.

6. Your company processes gigabytes of image thumbnails every day and stores them in your on-premises data centre. Your team developed an application that uses these image thumbnails withGCP services such as AutoML vision and pre-trained Vision API models to detect emotion,understand text and much more. The Cloud Security team has created a service account with theappropriate level of access; however, your team is unaware of how to authenticate to the GCPServices and APIs using the service account. What should you do?

    * A. Run gcloud iam service-accounts keys create to generate a JSON key 􀃕le for the serviceaccount and con􀃕gure your on-premises application to present the JSON key 􀃕le.
    * B. Con􀃕gure your on-premises application to use the service account username andpassword credentials.
    * C. Create an IAM user with the appropriate permissions and use the username and
password in your on-premises application.
    * D. Con􀃕gure the Direct interconnect to authenticate requests from your on-premisesnetwork automatically.

7. A Data Support Engineer at your company accidentally disclosed customer PII data in a supportcase in Google Cloud Console. Your compliance team wants to prevent this from occurring againand has asked you to set them up as approvers for cases raised by support teams. You want tofollow Google Best Practices. What IAM access should you grant them?

    * A. Grant roles/iam.roleAdmin IAM role to the compliance team group.
    * B. Grant roles/accessapprovalapprover IAM role to the compliance team group.
    * C. Grant roles/iam.roleAdmin IAM role to all members of the compliance team.
    * D. Grant roles/accessapprovalapprover IAM role to all members of the compliance team.

8. You created a deployment manager template to automate the provisioning of a productionGoogle Kubernetes Engine (GKE) cluster. The GKE cluster requires a monitoring pod running oneach node (DaemonSet) in daemon-system namespace, and your manager has asked you toidentify if it is possible to automate the provisioning of the monitoring pod along with the clusterusing the least number of resources. How should you do this?

    * A. Update the deployment manager template to add a metadata tag with key: daemon-system and value: DaemonSet manifest YAML.
    * B. Have the Runtime Con􀃕gurator create a RuntimeCon􀃕g resource with the DaemonSetde􀃕nition.
    * C. Add a new type provider in Deployment Manager for Kubernetes APIs and use the newtype provider to create the DaemonSet resource.
    * D. Update the deployment manager template to provision a preemptable compute engineinstance and con􀃕gure its startup script to use kubectl to create the DaemonSet.

9. Your company has two GCP organizations – one for development (and test) resources, andanother for production resources. Each GCP organization has a billing account and several GCPprojects. The new CFO doesn’t like this billing structure and has asked your team to consolidatecosts from all GCP projects onto a single invoice as soon as possible. What should you do?

    * A. Move all the projects from production GCP organization into development GCPorganization and link them to the development billing account.
    * B. Move all projects from both organizations into a new GCP organization and link all theprojects to a new billing account in the new GCP organization.
    * C. Link all projects from production GCP organization to the billing account used bydevelopment GCP organization.
    * D. Have both the billing account export their billing data to a single BigQuery dataset

