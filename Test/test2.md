# Google Associate Cloud Engineer Practice 
# Exam Part - 6

1. Your company has a massive quantity of unstructured data in text, Apache AVRO and PARQUET􀃕les in the on-premise data centre and wants to transform this data using a Data􀃖ow job andmigrate cleansed/enriched data to BigQuery. How should you make the on-premise 􀃕lesaccessible to Cloud Data􀃖ow?
A. Migrate the data from the on-premises data centre to Cloud Spanner by using theupload 􀃕les function.
B. Migrate the data from the on-premises data centre to Cloud SQL for MySQL by using theupload 􀃕les function.
C. Migrate the data from the on-premises data centre to Cloud Storage by using a customscript with gsutil commands.
D. Migrate the data from the on-premises data centre to BigQuery by using a custom scriptwith bq commands.
10. Your business-critical application deployed on a compute engine instance in us-west 1-a zonesu􀃠ered an outage due to GCP zone failure. You want to modify the application to be immune tozone failures while minimizing costs. What should you do?
A. Direct the tra􀃞c through a Global HTTP(s) Load Balancer to shield your application fromGCP zone failures.
B. Provision another compute engine instance in us-west1-b and balance the tra􀃞c acrossboth zones.
C. Ensure you have hourly snapshots of the disk in Google Cloud Storage. In the unlikely
event of a zonal outage, use the snapshots to provision a new Compute Engine Instance ina di􀃠erent zone.
D. Replace the single instance with a Managed Instance Group (MIG) and autoscalingenabled. Con􀃕gure a health check to detect failures rapidly.
11. You deployed a mission-critical application on Google Compute Engine. Your operations teamhave asked you to enable measures to prevent engineers from accidentally destroying theinstance. What should you do?
A. Turn on deletion protection on the compute engine instance.
B. Uncheck “Delete boot disk when instance is deleted” option when provisioning thecompute engine instance.
C. Deploy the application on a preemptible compute engine instance.
D. Enable automatic restart on the instance.
12. Your production applications are distributed across several Google Cloud Platform (GCP)projects, and your operations team want to e􀃞ciently manage all the production projects andapplications using gcloud SDK on Cloud Shell. What should you recommend they do to achievethis in the fewest possible steps?
A. Create a gcloud con􀃕guration for each production project. To manage resources of aparticular project, run gcloud init to update and initialize the relevant gcloud con􀃕guration.
B. Use the default gcloud con􀃕guration on cloud shell. To manage resources of a particularproject, activate the relevant gcloud con􀃕guration.
C. Create a gcloud con􀃕guration for each production project. To manage resources of aparticular project, activate the relevant gcloud con􀃕guration.
D. Use the default gcloud con􀃕guration on cloud shell. To manage resources of a particularproject, run gcloud init to update and initialize the relevant gcloud con􀃕guration.

13. You want to optimize the storage costs for long term archival of logs. Logs are accessedfrequently in the 􀃕rst 30 days and only retrieved after that if there is any special requirement inthe annual audit. The auditors may need to look into log entries of the previous three years. Whatshould you do?
A. Store the logs in Nearline Storage Class and set up a lifecycle policy to transition the 􀃕lesolder than 30 days to Archive Storage Class.
B. Store the logs in Standard Storage Class and set up a lifecycle policy to transition the 􀃕lesolder than 30 days to Archive Storage Class.
C. Store the logs in Standard Storage Class and set up lifecycle policies to transition the 􀃕les
older than 30 days to Coldline Storage Class, and 􀃕les older than 1 year to Archive StorageClass.
D. Store the logs in Nearline Storage Class and set up lifecycle policies to transition the 􀃕lesolder than 30 days to Coldline Storage Class, and 􀃕les older than 1 year to Archive StorageClass.

14. Your company runs most of its compute workloads in Google Compute Engine in the europe-west1-b zone. Your operations team use Cloud Shell to manage these instances. They want toknow if it is possible to designate a default compute zone and not supply the zone parameterwhen running each command in the CLI. What should you do?
A. In GCP Console set europe-west1-! zone in the default location in Compute EngineSettings.
B. Run gcloud con􀃕g to set europe-west1-b as the default zone.
C. Update the gcloud con􀃕guration 􀃕le ~/con􀃕g.ini to set europe-west1-b as the defaultzone.
D. Add a metadata entry in the Compute Engine Settings page with key: compute/zone andvalue: europe-west1-b.

15. You run a business-critical application in a Google Cloud Compute Engine instance, and youwant to set up a cost-e􀃞cient solution for backing up the data on the boot disk. You want asolution that:
minimizes operational overhead
– backs up boot disks daily
. allows quick restore of the backups when needed, e.g. disaster scenarios
. deletes backups older than a month automatically.
What should you do?
A. Enable Snapshot Schedule on the disk to enable automated snapshots per schedule.
B. Deploy a Cloud Function to initiate the creation of instance templates for all instancesdaily.
C. Con􀃕gure a Cloud Task to initiate the creation of images for all instances daily andupload them to Cloud Storage.
D. Set up a cron job with a custom script that uses gcloud APIs to create a new disk fromexisting instance disk for all instances daily.

16. The operations manager has asked you to identify the IAM users with Project Editor role onthe GCP production project. What should you do?
A. Turn on IAM Audit logging and build a Cloud Monitoring dashboard to display thisinformation.
B. Extract all project-wide SSH keys.
C. Execute gcloud projects get-iam-policy to retrieve this information.
D. Check the permissions assigned in all Identity Aware Proxy (IAP) tunnels.
17. Your company’s compute workloads are split between the on-premises data centre andGoogle Cloud Platform. The on-premises data centre is connected to Google Cloud network byCloud VPN. You have a requirement to provision a new non-publicly-reachable compute engineinstance on a c2-standard-8 machine type in australia-southeast1- zone. What should you do?
A. Con􀃕gure a route to route all tra􀃞c to the public IP of compute engine instance throughthe VPN tunnel.
B. Provision the instance without a public IP address.
C. Provision the instance in a subnet that has Google Private Access enabled.
D. Provision the instance in a subnetwork that has all egress tra􀃞c disabled.

18. You manage an overnight batch job that uses 20 VMs to transfer customer information from aCRM system to BigQuery dataset. The job can tolerate some VMs going down. The current highcost of the VMs make the overnight job not viable, and you want to reduce the costs. What shouldyou do?
A. Use preemptible compute engine instances to reduce cost.
B. Use a 􀃖eet of f1-micro instances behind a Managed Instances Group (MIG) withautoscaling. Set minimum and maximum nodes to 20.
C. Use tiny f1-micro instances to reduce cost.
D. Use a 􀃖eet of f1-micro instances behind a Managed Instances Group (MIG) withautoscaling and minimum nodes set to 1.

19. You plan to deploy an application to Google Compute Engine instance, and it relies on makingconnections to a Cloud SQL database for retrieving information about book publications. Tominimize costs, you are developing this application on your local workstation, and you want it toconnect to a Cloud SQL instance. Your colleague suggested setting up Application DefaultCredentials on your workstation to make the transition to Google Cloud easier. You are nowready to move the application to Google Compute Engine instance. You want to follow Googlerecommended practices to enable secure IAM access. What should you do?
A. Grant the necessary IAM roles to a service account, download the JSON key 􀃕le andpackage it with your application.
B. Grant the necessary IAM roles to the service account used by Google Compute Engineinstance.
C. Grant the necessary IAM roles to a service account and con􀃕gure the application runningon Google Compute Engine instance to use this service account.
D. Grant the necessary IAM roles to a service account, store its credentials in a con􀃕g 􀃕leand package it with your application.

2. You want to run an application in Google Compute Engine in the app-tier GCP project and haveit export data from Cloud Bigtable to daily-us-customer-export Cloud Storage bucket in the data-warehousing project. You plan to run a Cloud Data􀃖ow job in the data-arehousing project to pickup data from this bucket for further processing. How should you design the IAM access to enablethe compute engine instance push objects to daily-us-customer-export Cloud Storage bucket inthe data-warehousing project?
A. Update the access control on daily-us-customer-export Cloud Storage bucket to make itpublic. Create a subfolder inside the bucket with a randomized name and have thecompute engine instance push objects to this folder.
B. Ensure both the projects are in the same GCP folder in the resource hierarchy.
C. Grant the service account used by the compute engine in app-tier GCP projectroles/storage.objectCreator IAM role on the daily-us-customer-export Cloud Storagebucket.
D. Grant the service account used by the compute engine in app-tier GCP projectroles/storage.objectCreator IAM role on app-tier GCP project.

20. You run a batch job every month in your on-premises data centre that downloads clickstreamlogs from Google Cloud Storage bucket, enriches the data and stores them in Cloud BigTable. Thejob runs for 32 hours on average, can be restarted if interrupted, and must complete. You want tomigrate this batch job onto a cost-e􀃞cient GCP compute service. How should you deploy it?
A. Deploy the batch job in a GKE Cluster with preemptible VM node pool.
B. Deploy the batch job on a 􀃖eet of Google Cloud Compute Engine preemptible VM in aManaged Instances Group (MIG) with autoscaling.
C. Deploy the batch job on a Google Cloud Compute Engine Preemptible VM.
D. Deploy the batch job on a Google Cloud Compute Engine non-preemptible VM. Restartinstances as required.

21. Your gaming backend uses Cloud Spanner to store leaderboard and player pro􀃕le data. Youwant to scale the spanner instances based on predictable usage patterns. What should you do?
A. Con􀃕gure alerts in Cloud Monitoring to alert Google Operations Support team and havethem use their scripts to scale up or scale down the spanner instance as necessary.
B. Con􀃕gure a Cloud Scheduler job to invoke a Cloud Function that reviews the relevantCloud Monitoring metrics and resizes the Spanner instance as necessary.
C. Con􀃕gure alerts in Cloud Monitoring to trigger a Cloud Function via webhook, and havethe Cloud Function scale up or scale down the spanner instance as necessary.
D. Con􀃕gure alerts in Cloud Monitoring to alert your operations team and have themmanually scale up or scale down the spanner instance as necessary.

22. You are running an application on a Google Compute Engine instance. You want tocreatemultiple copies of this VM to handle the burst in tra􀃞c. What should you do?
A. Create a snapshot of the compute engine instance disk and create images from thissnapshot to handle the burst in tra􀃞c.
B. Create a snapshot of the compute engine instance disk and create instances from thissnapshot to handle the burst in tra􀃞c.
C. Create a snapshot of the compute engine instance disk, create a custom image from thesnapshot, create instances from this image to handle the burst in tra􀃞c.
D. Create a snapshot of the compute engine instance disk, create custom images from thesnapshot to handle the burst in tra􀃞c.

23. You migrated a mission-critical application from the on-premises data centre to GoogleKubernetes Engine (GKE) which uses e2-standard-2 machine types. You want to deploy additionalpods on c2-standard-16 machine types. How can you do this without causing applicationdowntime?
A. Run gcloud container clusters upgrade to move to c2-standard– 16 machine types.Terminate all existing pods.
B. Create a new GKE cluster with node pool instances of type c2-standard- – 16. Deploy theapplication on the new GKE cluster and delete the old GKE Cluster.
C. Create a new GKE cluster with two node pools – one with e2-standard-2 machine typesand other with c2-standard-16 machine types. Deploy the application on the new GKEcluster and delete the old GKE Cluster.
D. Update the existing cluster to add a new node pool with c2-standard-16 machine typesand deploy the pods.

24. You are migrating a complex on-premises data warehousing solution to Google Cloud. Youplan to create a 􀃖eet of Google Compute Engine instances behind a Managed Instances Group(MIG) in the app-tier project, and BigQuery in the data-warehousing project. How should youcon􀃕gure the service accounts used by Compute Engine instances to allow them query access toBigQuery datasets?
A. Grant the compute engine service account roles/bigquery.dataViewer role on the data-warehousing GCP project.
B. Grant the compute engine service account roles/owner on data-warehousing GCPproject.
C. Grant the compute engine service account roles/owner on data-warehousing GCPproject and roles/biqquery.dataViewer role on the app-tier GCP project.
D. Grant the BigQuery service account roles/owner on app-tier GCP project.

25. You deployed the Finance teams’ Payroll application to Google Compute Engine, and thisapplication is used by sta􀃠 during regular business hours. The operations team want to backupthe VMs daily outside the business hours and delete images older than 50 days to save costs.They need an automated solution with the least operational overhead and the least number ofGCP services. What should they do?
A. Navigate to the Compute Engine Disk section of your VM instance in the GCP console andenable a snapshot schedule for automated creation of daily snapshots. Set Auto-Deletesnapshots after to 50 days.
B. Add a metadata tag on the Google Compute Engine instance to enable snapshotcreation. Add a second metadata tag to specify the snapshot schedule, and a thirdmetadata tag to specify the retention period.
C. Use Cloud Scheduler to trigger a Cloud Function that creates snapshots of the disk daily.Use Cloud Scheduler to trigger another Cloud Function that iterates over the snapshots anddeletes snapshots older than 50 days.
D. Use AppEngine Cron service to trigger a custom script that creates snapshots of the diskdaily. Use AppEngine Cron service to trigger another custom script that iterates over thesnapshots and deletes snapshots older than 50 days.

26. Your compliance team wants to review the audit logs and data access logs in the productionGCP project. You want to follow Google recommended practices. What should you do?
A. Grant the compliance team a custom IAM role that has logging.privateLogEntries. listpermission. Let the compliance team know they can also query IAM policy changes in CloudLogging.
B. Export logs to Cloud Storage and grant the compliance team a custom IAM role that has
logging.privateLogEntries.list permission.
C. Export logs to Cloud Storage and grant the compliance teamroles/logging.privateLogViewer lAMrole.
D. Grant the compliance team roles/logging.privateLogViewer\AM role. Let the complianceteam know they can also query IAM policy changes in Cloud Logging.

27. You want to migrate a legacy application from your on-premises data centre to Google CloudPlatform. The application serves SSL encrypted tra􀃞c from worldwide clients on TCP port 443.What GCP Loadbalancing service should you use to minimize latency for all clients?
A. External HTTP(S) Load Balancer.
B. Internal TCP/UDP Load Balancer.
C. Network TCP/UDP Load Balancer.
D. SSL Proxy Load Balancer.

28. You are deploying an application on the Google Compute Engine, and you want to minimizenetwork egress costs. The organization has a policy that requires you to block all but essentialegress tra􀃞c. What should you do?
A. Enable a 􀃕rewall rule at priority 100 to allow essential egress tra􀃞c.
B. Enable a 􀃕rewall rule at priority 100 to allow ingress and essential egress tra􀃞c.
C. Enable a 􀃕rewall rule at priority 100 to block all egress tra􀃞c, and another 􀃕rewall rule atpriority 65534 to allow essential egress tra􀃞c.
D. Enable a 􀃕rewall rule at priority 65534 to block all egress tra􀃞c, and another 􀃕rewall ruleat priority 100 to allow essential egress tra􀃞c.

29. You work for a startup company where every developer has a dedicated development GCPproject linked to a central billing account. Your 􀃕nance lead is concerned that some developersmay leave some services running unnecessarily or may not understand the cost implications ofturning on speci􀃕c services in Google Cloud Platform. They want to be alerted when a developerspends more than 750$ per month in their GCP project. What should you do?
A. Export Billing data from each development GCP projects to a separate BigQuery dataset.On each dataset, use a Data Studio dashboard to plot the spending.
B. Set up a budget for each development GCP projects. For each budget, trigger an emailnoti􀃕cation when the spending exceeds $750.
C. Export Billing data from all development GCP projects to a single BigQuery dataset. Use a
Data Studio dashboard to plot the spend.
D. Set up a single budget for all development GCP projects. Trigger an email noti􀃕cationwhen the spending exceeds $750 in the budget.
3. Your company has deployed all its production applications in a single Google Cloud Project anduses several GCP projects for development and test environments. The operations team requiresaccess to all production services in this project to debug live issues and deploy enhancements.Your security team prevents the creation of IAM roles that automatically broaden to include newpermissions/services in future. How should you design the IAM role for operations team?
A. Create a custom role with the necessary permissions and grant the role on theproduction GCP project to all members of the operations team.
B. Grant the Project Editor role at the organization level to all members of the operationsteam.
C. Grant the Project Editor role on the production GCP project to all members of theoperations team.
D. Create a custom role with the necessary permissions and grant the role at theorganization level to all members of the operations team.
30. EU GDPR requires you to respond to a Subject Access Request (SAR) within one month. To becompliant, your company deployed an application that uses Apache WebServer to provide SARarchive (tar) 􀃕les back to customers requesting them. Your compliance team has asked you tosend them an email noti􀃕cation when the network egress charges for this server in the GCPproject exceeds 250 dollars per month. What should you do?
A. Export the logs from Apache server to Cloud Logging and deploy a Cloud Function toparse the logs, extract and sum up the size of response payload for all requests during thecurrent month; and send an email noti􀃕cation when spending exceeds $250.
B. Con􀃕gure a budget with the scope set to the billing account, the amount set to $250,threshold rule set to 100% of actual cost & trigger email noti􀃕cations when spendingexceeds the threshold.
C. Export the project billing data to a BigQuery dataset and deploy a Cloud Function toextract and sum up the network egress costs from the BigQuery dataset for the Apacheserver for the current month, and send an email noti􀃕cation when spending exceeds $250.
D. Con􀃕gure a budget with the scope set to the project, the amount set to $250, thresholdrule set to 100% of actual cost & trigger email noti􀃕cations when spending exceeds thethreshold.
31. You are running a business-critical application in a GKE cluster in a subnet with clusterautoscaling enabled. A massive surge in demand for your company’s products has seen the GKEcluster node pool scale-up until there were no more free IP addresses available for new VMs inthe subnet. What should you do to 􀃕x this issue?
A. Add a new subnet to the same region.
B. Add a secondary (alias) IP range to the existing subnet.
C. Add a new VPC and set up VPC sharing between the new and existing VPC.
D. Expand the range of the existing subnet.
32. You developed an application on App Engine Service to read data from a BigQuery datasetand convert the data to PARQUET format. The application is using the default app-engine serviceaccount in the app-tier GCP project. The data team owns the BigQuery dataset in the data-warehousing project. What IAM Access should you grant to the default app-engine serviceaccount in app-tier GCP project?
A. Grant the default app-engine service account in the app-tier GCP project roles/bigquery.data Viewer role on the data-warehousing project.
B. Grant the service account in the data-warehousing GCP project roles/bigquery.job Userrole on the app-tier project.
C. Grant the default app-engine service account in the app-tier GCP projectroles/bigquery.dataViewer role on the same project.
D. Grant the default app-engine service account in the app-tier GCP projectroles/bigquery.jobUser role on data-warehousing project.
33. Your company updated its business operating model recently and no longer need theapplications deployed in the data-analytics-v1 GCP project. You want to turn o􀃠 all GCP servicesand APIs in this project. You want to do this e􀃞ciently using the least number of steps whilefollowing Google recommended practices. What should you do?
A. Ask an engineer with Project Owner IAM role to identify all resources in the project anddelete them.
B. Ask an engineer with Project Owner IAM role to locate the project and shut down.
C. Ask an engineer with Organization Administrator IAM role to identify all resources in theproject and delete them.
D. Ask an engineer with Organization Administrator IAM role to locate the project and shutdown.
34. You deployed an application on a general-purpose Google Cloud Compute Engine instancethat uses a persistent zonal SSD of 300 GB. The application downloads large Apache AVRO 􀃕lesfrom Cloud Storage, retrieve customer details from them and saves a text 􀃕le on local disk foreach customer before pushing all the text 􀃕les to a Google Storage Bucket. These operationsrequire high disk I/O, but you 􀃕nd that the read and write operations on the disk are alwaysthrottled. What should you do to improve the throughput while keeping costs to a minimum?
A. Bump up the size of its SSD persistent disk to 1 TB.
B. Replace Zonal Persistent SSD with a Local SSD.
C. Replace Zonal Persistent SSD with a Regional Persistent SSD.
D. Bump up the CPU allocated to the general-purpose Compute Engine instance.
35. You want to monitor resource utilization (RAM, Disk, Network, CPU, etc.) for all applications indevelopment, test and production GCP projects in a single dashboard. What should you do?
A. In Cloud Monitoring, share charts from development, test and production GCP projects.
B. Create a Cloud Monitoring workspace in the production project and add developmentand test projects to it.
C. Make use of the default Cloud Monitoring dashboards in all the projects.
D. Grant roles/monitoring.admin to development, test and production GCP projects.
36. You have an application in your on-premises data centre with an API that is triggered when anew 􀃕le is created or updated in a NAS share. You want to migrate this solution to Google CloudPlatform and have identi􀃕ed Cloud Storage as the replacement service for NAS. How should youdeploy the API?
A. Deploy the API on GKE cluster and use Cloud Scheduler to trigger the API to look for 􀃕lesin Cloud Storage there were created or update since the last run.
B. Trigger a Cloud Function whenever 􀃕les in Cloud Storage are created or updated.
C. Trigger a Cloud Data􀃖ow job whenever 􀃕les in Cloud Storage are created or updated.
D. Con􀃕gure Cloud Pub/Sub to capture details of 􀃕les created/modi􀃕ed in Cloud Storage.Deploy the API in App Engine Standard and use Cloud Scheduler to trigger the API to fetchinformation from Cloud Pub/Sub.
37. You are running a business-critical application in a 􀃖eet of compute engine instances behindan autoscaled Managed Instances Group (MIG). The MIG initiated a scale-up event to keep upwith the increasing incoming tra􀃞c, but the compute engine instance failed to create. Howshould you debug this issue?
A. 1. Ensure you don’t have any persistent disks with the same name as the VM instance. 2.Ensure the disk autodelete property is turned on (disks.autoDelete set to true). 3. Ensureinstance template syntax is valid.
B. 1. Ensure instance template syntax is valid. 2. Ensure the instance template, instance andthe persistent disk names do not con􀃖ict.
C. 1. Ensure the instance template, instance and the persistent disk names do not con􀃖ict.2. Ensure the disk autodelete property is turned on (disks.autoDelete set to true).
D. 1. Ensure you don’t have any persistent disks with the same name as the VM instance. 2.Ensure instance template syntax is valid.
38. You work for a multinational car insurance company that specializes in rewarding saferdrivers with cheaper premiums. Your company does this by installing black box loT devices in its 2million insured drivers’ cars. These devices capture driving behaviours such asacceleration/deceleration, speed compared to speed limits, and types of driving, such ascommuting on freeway compared to commuting on surface streets etc. You expect to receivehundreds of events per minute from every device. You need to store this data and retrieve dataconsistently based on the event time, and both operations should be atomic. How should youstore this data?
A. Store the data in Cloud Storage. Have a 􀃕le per loT device and append new data to the􀃕le.
B. Store the data in Cloud Datastore. Have an entity group per device.
C. Store the data in Cloud BigTable. Have a row key based on the ingestion timestamp.
D. Store the data in Cloud Filestore. Have a 􀃕le per loT device and append new data to the􀃕le.
39. Your team creates/updates the infrastructure for all production requirements. You need toimplement a new change to the current infrastructure and want to preview the update to the restof your team before committing the changes. You want to follow Google- recommendedpractices. What should you?
A. Clone the production environment to create a staging environment and deploy theproposed changes to the staging environment. Execute gcloud compute instances list toview the changes and store the results in a Google Cloud Storage bucket.
B. Preview the updates using Deployment Manager and store the results in a Google CloudStorage bucket.
C. Clone the production environment to create a staging environment and deploy theproposed changes to the staging environment. Execute gcloud compute instances list to
view the changes and store the results in a Google Cloud Source Repository.
D. Preview the updates using Deployment Manager and store the results in a Google CloudSource Repository.

4. Your company is building a mobile application that enables users to upload and share imageswith their friends. Your company places a high value on security. Prefers minimal maintenance(no-op), and wants to optimize costs where possible. You are designing the backend for the appbased on these requirements:
– Enable users to upload images for only 30 minutes,
– Enable users to retrieve their images and share their images with their friends,
– Delete images older than 50 days.
You have very little time to design the solution and take it to production. What should you do?(Choose two)
A. Have the mobile application use signed URLs to enabled time- limited upload to CloudStorage.
B. Use Cloud Scheduler to trigger a Cloud Function to check for objects older than 50 daysand delete them.
C. Enable lifecycle policy on the bucket to delete objects older than 50 days.
D. Write a cron script that checks for objects older than 50 days and deletes them.
E. Have the mobile application send the images to an SFTP server.
40. An auditor requires speci􀃕c access on certain GCP services in your Cloud project. You havestarted working on the 􀃕rst version of a custom IAM role to enable this access. You are currentlytesting this role in a test GCP project. The compliance team requires this role to be production-ready, and want you to share with them the lifecycle stage. What should you do?
A. 1. Set the custom IAM role lifecycle stage to ALPHA while you test the role in the test GCPproject. 2. Restrict the custom IAM role to use permissions with TESTING support level.
B. 1. Set the custom IAM role lifecycle stage to BETA while you test the role in the test GCPproject. 2. Restrict the custom IAM role to use permissions with SUPPORTED support level.
C. 1. Set the custom IAM role lifecycle stage to BETA while you test the role in the test GCPproject. 2. Restrict the custom IAM role to use permissions with TESTING support level.
D. 1. Set the custom IAM role lifecycle stage to ALPHA while you test the role in the test GCPproject. 2. Restrict the custom IAM role to use permissions with SUPPORTED support level.
41. Your company stores an export of its Customer PII data in a multi-regional Google Cloudstorage bucket. Your legal and compliance department has asked you to record alloperations/requests on the data in this bucket. What should you do?
A. Enable the default Cloud Storage Service account exclusive access to read all operationsand record them.
B. Use the Data Loss Prevention API to record this information.
C. Use the Identity Aware Proxy API to record this information.
D. Turn on data access audit logging in Cloud Storage to record this information.
42. A 􀃕nance analyst at your company is suspended pending an investigation into alleged􀃕nancial misconduct. However, their Gsuite account was not disabled immediately. Yourcompliance team has asked you to 􀃕nd out if the suspended employee has accessed any auditlogs or BigQuery datasets after their suspension. What should you do?
A. Search for users’ Cloud Identity username (email address) as the principal in systemevent logs in Cloud Logging.
B. Search for users’ Cloud Identity username (email address) as the principal in data accesslogs in Cloud Logging.
C. Search for users’ service account as the principal in admin activity logs in Cloud Logging.
D. Search for users’ service account as the principal in data access logs in Cloud Logging.
43. Your company wants to migrate all compute workloads from the on-premises data centre toGoogle Cloud Compute Engine. A third-party team provides operational support for yourproduction applications outside business hours. Everyone at your company has a Gsuite account,but the support team do not. How should you grant them access to the VMs?
A. Use Cloud Identity Aware Proxy (IAP) to enable SSH tunnels to the VMs and add the third-party team as a tunnel user.
B. Set up a 􀃕rewall rule to open SSH port (TCP:22) to the IP range of the third-party team.
C. Set up a Cloud VPN tunnel between the third-party network and your production GCPproject.
D. Add all the third party teams SSH keys to the production compute engine instances.
44. All departments at your company have their own Google Cloud Projects. You got transferredinto a new department that doesn’t have a project yet, and you are ready to deploy a newapplication onto a Compute Engine Instance. What should you do?
A. In the GCP Console, enable the Compute Engine API. When creating a new instance in theconsole, select the checkbox to create the instance in a new GCP project and provide theproject name and ID.
B. Use gcloud commands 􀃕rst to create a new project, then to enable the Compute EngineAPI and 􀃕nally, to launch a new compute engine instance in the project.
C. Run gcloud compute instances create with –project 􀃖ag to automatically create the newproject and a compute engine instance. When prompted to enable the Compute EngineAPI, select Yes.
D. In the GCP Console, enable the Compute Engine API. Run gcloud compute instancescreate with – –project 􀃖ag to automatically create the new project and a compute engineinstance.
45. You deployed an application using Apache Tomcat server on a single Google Cloud VM. Usersare complaining of intermittent issues accessing a speci􀃕c page in the application, and you wantto look at the logs on the local disk. What should you do?
A. Con􀃕gure a health check on the instance to identify the issue and email you the logswhen the application experiences the issue.
B. Check logs in Cloud Logging.
C. Check logs in the Serial Console.
D. Install the Cloud Logging Agent on the VM and con􀃕gure it to send logs to Cloud Logging.Check logs in Cloud Logging.
46. Your company plans to migrate all applications from the on-premise data centre to GoogleCloud Platform and requires a monthly estimate of the cost of running these applications in GCP.How can you provide this estimate?
A. For all GCP services/APIs you are planning to use, use the GCP pricing calculator toestimate the monthly costs.
B. For all GCP services/APIs you are planning to use, capture the pricing from the productspricing page and use an excel sheet to estimate the monthly costs.
C. Migrate all applications to GCP and run them for a week. Use the costs from the BillingReport page for this week to extrapolate the monthly cost of running all applications inGCP.
D. Migrate all applications to GCP and run them for a week. Use Cloud Monitoring toidentify the costs for this week and use it to derive the monthly cost of running allapplications in GCP.
5. Your company uses Google Cloud for all its compute workloads. One of the applications thatyou developed has passed unit testing, and you want to use Jenkins to deploy the application inUser Acceptance Testing (UAT) environment. Your manager has asked you to automate Jenkinsinstallation as quickly and e􀃞ciently as possible. What should you do?
A. Deploy Jenkins on a 􀃖eet of Google Cloud Compute Engine VMs in a Managed InstancesGroup (MIG) with autoscaling.
B. Deploy Jenkins on a Google Compute Engine VM.
C. Use GCP Marketplace to provision Jenkins.
D. Deploy Jenkins on a GKE Cluster.
6. Your company deployed its applications across hundreds of GCP projects that use di􀃠erentbilling accounts. The 􀃕nance team is struggling to add up all production Cloud Opex costs and hasrequested your assistance for enabling/providing a single pane of glass for all costs incurred byall applications in Google Cloud. You want to include new costs as soon as they become available.What should you do?
A. Use Google pricing calculator for all the services used in all GCP projects and pass theestimated cost to 􀃕nance team every month.
B. Enable Billing Export from all GCP projects to BigQuery and ask the 􀃕nance team to useGoogle Data Studio to visualize the data.
C. Ask the 􀃕nance team to check reports view section in Cloud Billing Console.
D. Use Cloud Scheduler to trigger a Cloud Function every hour. Have the Cloud Functiondownload the CSV from the Cost Table page and upload the data to BigQuery. Ask the􀃕nance team to use Google Data Studio to visualize the data.
7. Your production Compute workloads are running in a subnet with a range 192.168.20.128/25.A recent surge in tra􀃞c has seen the production VMs struggle, and you want to add more VMs,but there are no free IP addresses in the VPC. All new and old VMs need to communicate witheach other. How can you do this with the fewest steps?
A. Create a new VPC and a new subnet with IP range 192.168.21.0/24. Enable VPC Peeringbetween the old VPC and new VPC. Con􀃕gure a custom Route exchange.
B. Create a new VPC network and a new subnet with IP range 192.168.21.0/24. Enable VPCPeering between the old VPC and new VPC.
C. Create a new non-overlapping Alias range in the existing VPC and Con􀃕gure the VMs touse the alias range.
D. Update the subnet range to 192.168.20.0/24.
8. Your compliance team has asked you to set up an external auditor access to logs from all GCPprojects for the last 60 days. The auditor wants to combine, explore and analyze the contents ofthe logs from all projects quickly and e􀃞ciently. You want to follow Google Recommendedpractices. What should you do?
A. Set up a Cloud Storage sink destination to export logs from all the projects to a bucket.Con􀃕gure a lifecycle rule to delete objects older than 60 days. Ask the auditor to query logsfrom the bucket.
B. Set up a Cloud Scheduler job to trigger a Cloud Function that reads and export logs fromall the projects to a BigQuery dataset. Con􀃕gure the table expiration on the dataset to 60days. Ask the auditor to query logs from the dataset.
C. Set up a BigQuery sink destination to export logs from all the projects to a dataset.Con􀃕gure the table expiration on the dataset to 60 days. Ask the auditor to query logs fromthe dataset.
D. Ask the auditor to query logs from Cloud Logging.
9. You work for a multinational delivery services company that uses Apache Cassandra DB as thebackend store for its delivery track and trace system. The existing on-premises data centre is outof space. To cope with an anticipated increase in requests in the run-up to Christmas, you want tomove this application rapidly to Google Cloud with minimal e􀃠ort whilst ensuring you can spin upmultiple stacks (development, test, production) and isolate them from each other. How can youdo this?
A. Download the installation guide for Cassandra on GCP and follow the instructions toinstall the database.
B. Launch Cassandra DB from Cloud Marketplace.
C. Install an instance of Cassandra DB on Google Cloud Compute Engine, take a snapshot ofthis instance and use the snapshot to spin up additional instances of Cassandra DB.
D. Install an instance of Cassandra DB on Google Cloud Compute Engine, take a snapshotof this instance and upload to Google Cloud Storage bucket. Every time you need a newinstance of Cassandra DB, spin up a new compute engine instance from the snapshot.
