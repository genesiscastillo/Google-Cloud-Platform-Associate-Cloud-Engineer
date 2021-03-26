ExamPart 4

1. You developed an application that reads objects from a cloud storage bucket. You followedGCP documentation and created a service account with just the permissions to read objects fromthe cloud storage bucket. However, when your application uses this service account, it fails toread objects from the bucket. You suspect this might be an issue with the permissions assignedto the service account. You would like to authenticate a gsutil session with the service accountcredentials, reproduce the issue yourself and identify the root cause. How can you authenticategsutil with service account credentials?
A. Create JSON keys for the service account and execute gcloud authenticate service-account –key-􀃕le [KEY_FILE].
B. Create JSON keys for the service account and execute gcloud authenticateactivate-service-account –key-􀃕le [KEY_FILE].
C. Create JSON keys for the service account and execute gcloud auth activate-service-account –key-􀃕le [KEY_FILE].
D. Create JSON keys for the service account and execute gcloud auth service- account – –key-􀃕le [KEY_FILE].
10. You have an application deployed in a GKE Cluster as a Kubernetes workload with DaemonSets. Your application has become very popular and is now struggling to cope up with increasedtra􀃞c. You want to add more pods to your workload and want to ensure your cluster scales upand scales down automatically based on volume. What should you do?
A. Enable autoscaling on Kubernetes Engine.
B. Perform a rolling update to modify machine type from 11-standard-2 to n1- – standard-4.
C. Enable Horizontal Pod Autoscaling for the Kubernetes deployment.
D. Create another identical Kubernetes workload and split tra􀃞c between the twoworkloads.
11. You developed an application to serve production users and you plan to use Cloud SQL tohost user state data which is very critical for the application 􀃖ow. You want to protect your userstate data from zone failures. What should you do?
A. Create a Read replica in the same region but in a di􀃠erent zone.
B. Con􀃕gure High Availability (HA) for Cloud SQL and Create a Failover replica in the sameregion but in a di􀃠erent zone.
C. Create a Read replica in a di􀃠erent region.
D. Con􀃕gure High Availability (HA) for Cloud SQL and Create a Failover replica in a di􀃠erentregion.
12. Your Company is planning to migrate all Java web applications to Google App Engine.However, you still want to continue using your on-premise database. How can you set up the appengine to communicate with your on-premise database while minimizing e􀃠ort?
A. Setup the application using App Engine Flexible environment with Cloud Router toconnect to an on-premise database.
B. Setup the application using App Engine Standard environment with Cloud VPN toconnect to an on-premise database.
C. Setup the application using App Engine Standard environment with Cloud Router toconnect to an on-premise database.
D. Setup the application using App Engine Flexible environment with Cloud VPN to connectto an on-premise database.
13. You want to migrate an XML parser application from the on-premises data centre to GoogleCloud Platform. You created a development project, set up the necessary IAM roles and deployedthe application in a compute engine instance. The testing has succeeded, and you are ready todeploy the staging instance. You want to create the same IAM roles in a new staging GCP project.How can you do this e􀃞ciently without compromising security?
A. Make use of gcloud iam roles copy command to copy the IAM roles from theDevelopment GCP organization to the Staging GCP organization.
B. Make use of Create Role feature in GCP console to create all necessary IAM roles fromnew in the Staging project.
C. Make use of gcloud iam roles copy command to copy the IAM roles from theDevelopment GCP project to the Staging GCP project.
D. Make use of the Create Role from Role feature in GCP console to create IAM roles in theStaging project from the Development IAM roles.
14. Your company’s auditors carry out an annual audit every year and have asked you to providethem with all the IAM policy changes in Google Cloud since the last audit. You want to streamlineand expedite the analysis for audit. How should you share the information requested byauditors?
A. Export all audit logs to Cloud Pub/Sub via an export sink. Use a Cloud Function to readthe messages and store them in Cloud SQL. Make use of ACLs and views to restrict the datashared with the auditors.
B. Export all audit logs to Google Cloud Storage bucket and set up the necessary IAM accesto restrict the data shared with auditors.
C. Export all audit logs to BigQuery dataset. Make use of ACLs and views to restrict the datashared with the auditors.
D. Have the auditors query the required information quickly. Con􀃕gure alerts in CloudMonitoring and trigger noti􀃕cations to the auditors.
15. You work at a large organization where each team has a distinct role. The development teamcan create Google Cloud projects but can’t link them to a billing account – this role is reserved forthe 􀃕nance team, and the development team do not want 􀃕nance team to make changes to theirproject resources. How should you con􀃕gure IAM access controls to enable this?
A. Grant the development team Billing Account User (roles/billing.user) role on the billingaccount and Project Billing Manager (roles/billing.projectManager) on the GCP organization.
B. Grant the 􀃕nance team Billing Account User (roles/billing.user) role on the billing accountand Project Billing Manager roles/billing.projectManager) on the GCP organization.
C. Grant the 􀃕nance team Billing Account User (roles/billing.user) role on the billingaccount.
D. Grant the development team Billing Account User (roles/billing.user) role on the billingaccount.
16. You have a number of applications that have bursty workloads and are heavily dependent ontopics to decouple publishing systems from consuming systems. Your company would like to goserverless to enable developers to focus on writing code without worrying about infrastructure.Your solution architect has already identi􀃕ed Cloud Pub/Sub as a suitable alternative fordecoupling systems. You have been asked to identify a suitable GCP Serverless service that iseasy to use with Cloud Pub/Sub. You want the ability to scale down to zero when there is notra􀃞c in order to minimize costs. You want to follow Google recommended practices. Whatshould you suggest?
A. Cloud Run for Anthos
B. Cloud Run
C. App Engine Standard
D. Cloud Functions.
17. You deployed a Java application on four Google Cloud Compute Engine VMs in two zonesbehind a network load balancer. During peak usage, the application has stuck threads. This issueultimately takes down the whole system and requires a reboot of all VMs. Your operations teamhave recently heard about self-healing mechanisms in Google Cloud and have asked you toidentify if it is possible to automatically recreate the VMs if they remain unresponsive for 3attempts 10 seconds apart. What should you do?
A. Enable autoscaling on the Managed Instance Group (MIG).
B. Enable autohealing and set the autohealing health check to healthy (HTTP).
C. Use a global HTTP(s) Load Balancer instead and limit Requests Per Second (RPS) to 10.
D. Use a global HTTP(s) Load Balancer instead and set the load balancer health check tohealthy (HTTP).
18. You’ve created a Kubernetes engine cluster named “my-gcp-ace-proj-1”, which has a clusterpool named my-gcp-ace-primary-node-pool. You want to increase the number of nodes withinyour cluster pool from 10 to 20 to meet capacity demands. What is the command to change thenumber of nodes in your pool?
A. gcloud container clusters update my-gcp-ace-proj-1 – -node-pool my-gcp-ace- primary-node-pool -num-nodes 20
B. gcloud container clusters resize my-gcp-ace-proj- 1 – -node-pool my-gcp-ace- primary-node-pool -new-size 20
C. gcloud container clusters resize my-gcp-ace-proj- 1 – -node-pool my-gcp-ace-primary-node-pool -num-nodes 20
D. kubectl container clusters update my-gcp-ace-proj-1 – -node-pool my-gcp-ace- primary-node-pool–num-nodes 20
19. A company wants to build an application that stores images in a Cloud Storage bucket andwants to generate thumbnails as well as resize the images. They want to use a google managedservice that can scale up and scale down to zero automatically with minimal e􀃠ort. You have beenasked to recommend a service. Which GCP service would you suggest?
A. Google Compute Engine
B. Google App Engine
C. Cloud Functions
D. Google Kubernetes Engine
2. Your company is migrating a mission-critical application from the on-premises data centre toGoogle Cloud Platform. The application requires 12 Compute Engine VMs to handle tra􀃞c at peakusage times. Your operations team have asked you to ensure the VMs restart automatically (i.e.without manual intervention) if/when they crash, and the processing capacity of the applicationdoes not reduce down during system maintenance. What should you do?
A. Deploy the application on a Managed Instance Group (MIG) that disables the creationretry mode by setting the -nocreation-retries 􀃖ag.
B. Create an instance template with availability policy that turns o􀃠 the automatic restartbehaviour and sets on-host maintenance to terminate instances during maintenanceevents. Deploy the application on a Managed Instance Group (MIG) based on this template.
C. Deploy the application on a Managed Instance Group (MIG) with autohealing healthcheck set to healthy (HTTP).
D. Create an instance template with availability policy that turns on the automatic restartbehaviour and sets on-host maintenance to live migrate instances during maintenanceevents. Deploy the application on a Managed Instance Group (MIG) based on this template.
20. You want to ensure the boot disk of a preemptible instance is persisted for re-use. Howshould you provision the gcloud compute instance to ensure your requirement is met.
A. gcloud compute instances create [INSTANCE_NAME] -preemptible. The 􀃖ag — boot-disk-auto-delete is disabled by default.
B. gcloud compute instances create [INSTANCE_NAME] -preemptible — -boot-disk- auto-delete=no
C. gcloud compute instances create [INSTANCE_NAME] –preemptible — no-boot-disk-auto-delete
D. gcloud compute instances create [INSTANCE_NAME] -no-auto-delete
21. You want to ingest and analyze large volumes of stream data from sensors in real- time,matching the high speeds of loT data to track normal and abnormal behavior. You want to run itthrough a data processing pipeline and store the results. Finally, you want to enable customers tobuild dashboards and drive analytics on their data in real-time. What services should you use forthis task?
A. Cloud Pub/Sub, Cloud Data􀃖ow, Cloud Dataprep
B. Stackdriver, Cloud Data􀃖ow, BigQuery
C. Cloud Pub/Sub, Cloud Data􀃖ow, Cloud Dataproc
D. Cloud Pub/Sub, Cloud Data􀃖ow, BigQuery
22. Your company is migrating an application from its on-premises data centre to Google Cloud.One of the applications uses a custom Linux distribution that is not available on Google Cloud.Your solution architect has suggested using VMWare tools to exporting the image and store it in aCloud Storage bucket. The VM Image is a single compressed 64 GB tar 􀃕le. You started copyingthis 􀃕le using gsutil over a dedicated 1Gbps network, but the transfer is taking a very long time tocomplete. Your solution architect has suggested using all of the 1Gbps Network to transfer the􀃕le quickly. What should you do?
A. Use parallel composite uploads to speed up the transfer.
B. Upload the 􀃕le Multi-Regional instead and move the 􀃕le to Nearline Storage Class.
C. Restart the transfer from GCP console.
D. Increase the transfer speed by decreasing the TCP window size.
23. You want to migrate an application from Google App Engine Standard to Google App EngineFlex. Your application is currently serving live tra􀃞c and you want to ensure everything is workingin Google App Engine Flex before migrating all tra􀃞c. You want to minimize e􀃠ort and ensure theavailability of service. What should you do?
A. Set env: app-engine-􀃖ex in app.yaml 2. gcloud app deploy -no-promote -version=[NEW_VERSION] 3. Validate [NEW_VERSION] in App Engine Flex 4. gcloud app versions start[NEW_VERSION]
B. Set env: app-engine-􀃖ex in app.yaml 2. gcloud app deploy –version=[NEW_VERSION] 3.Validate [NEW_VERSION] in App Engine Flex 4. gcloud app versions start [NEW_VERSION]
C. Set env: 􀃖ex in app.yaml 2. gcloud app deploy–no-promote –version=[NEW_VERSION] 3.Validate [NEW_VERSION] in App Engine Flex 4. gcloud app versions migrate [NEW_VERSION]
D. Set env: 􀃖ex in app.yaml 2. gcloud app deploy –version=[NEW_VERSION] 3. Validate[NEW_VERSION] in App Engine Flex 4. gcloud app versions migrate [NEW_VERSION]
24. Your company collects and stores CCTV footage videos in raw format in Google Cloud Storage.Within the 􀃕rst 30 days, the footage is processed regularly for detecting patterns such asthreat/object/face detection and suspicious behavior detection. You want to minimize the cost ofstoring all the data in Google Cloud. How should you store the videos?
A. Use Google Cloud Regional Storage for the 􀃕rst 30 days, and use lifecycle rules totransition to Nearline Storage.
B. Use Google Cloud Nearline Storage for the 􀃕rst 30 days, and use lifecycle rules totransition to Coldline Storage.
C. Use Google Cloud Regional Storage for the 􀃕rst 30 days, and then move videos to GooglePersistent Disk.
D. Use Google Cloud Regional Storage for the 􀃕rst 30 days, and use lifecycle rules totransition to Coldline Storage.
25. You migrated an internal HR system from an on-premises database to Google Cloud ComputeEngine Managed Instance Group (MIG). The networks team at your company has asked you toassociate the internal DNS records of the VMs with a custom DNS zone. You want to followGoogle recommended practices. What should you do?
A. 1.Create a new Cloud DNS zone and a new VPC and associate the DNS zone with the VPC.2. When provisioning the VMs, associate the DNS records with the new DNS zone. 3.Con􀃕gure 􀃕rewall rules to block all external (public) tra􀃞c. 4. Finally, con􀃕gure the DNSzone associated with the default VPC to direct all requests to the new DNS zone.
B. 1.Provision the VMs with custom hostnames.
C. 1.Create a new Cloud DNS zone and set its visibility to private. 2. When provisioning theVMs, associate the DNS records with the new DNS zone.
D. 1.Install a new BIND DNS server on Google Compute Engine, using the BIND name serversoftware (BIND9). 2. Con􀃕gure a Cloud DNS forwarding zone to direct all requests to theInternal BIND DNS server. 3. When provisioning the VMs, associate the DNS records withthe Internal BIND DNS server.
27. Your team is working towards using the desired state con􀃕guration for your applicationdeployed on the GKE cluster. You have YAML 􀃕les for the Kubernetes Deployment and Serviceobjects. Your application is designed to have 2 pods, which is de􀃕ned by the replicas parameter inapp-deployment.yaml. Your service uses GKE Load Balancer which is de􀃕ned in app-service.yamlYou created the Kubernetes resources by running 1 kubectl apply -f app-deployment.yaml 2kubectl apply -f app-service.yaml Your deployment is now serving live tra􀃞c but is su􀃠ering fromperformance issues. You want to increase the number of replicas to 5. What should you do inorder to update the replicas in existing Kubernetes deployment objects?
A. Disregard the YAML 􀃕le. Enable autoscaling on the deployment to trigger on CPU usageand set max pods to 5. kubectl autoscale myapp—max=5–cpu- percent=80
B. Modify the current con􀃕guration of the deployment by using kubectl edit to open theYAML 􀃕le of the current con􀃕guration, modify and save the con􀃕guration. kubectl editdeployment/app-deployment-o yaml –save-con􀃕g
C. Disregard the YAML 􀃕le. Use the kubectl scale command to scale the replicas to 5.kubectl scale -replicas= -f app-deployment.yaml
D. Edit the number of replicas in the YAML 􀃕le and rerun the kubectl apply. kubectl apply -fapp-deployment.yaml
28. An application that you are migrating to Google Cloud relies on overnight batch jobs that takebetween 2 to 3 hours to complete. You want to do this at a minimal cost. Where should you runthese batch jobs?
A. Run the batch jobs in a non-preemptible shared core compute engine instance thatsupports short periods of bursting.
B. Run the batch jobs in a GKE cluster on a node pool with four instances of type f1-micro.
C. Run the batch jobs in a GKE cluster on a node pool with a single instance of type e2-small.
D. Run the batch jobs in a preemptible compute engine instance of appropriate machinetype.
29. You created a Kubernetes deployment by running kubectl run nginx – -image=nginx -replicas=1 After a few days, you decided you no longer want this deployment. You identi􀃕ed thepod and deleted it by running kubectl delete pod. You noticed the pod got recreated. $ kubectlget pods NAME READY STATUS RESTARTS AGE nginx-84748895c4-nqqmt 1/1 Running 0 9m41s $kubectl delete pod nginx-84748895c4-nqqmt pod “nginx-84748895c4-nqqat” deleted $ kubectl getpods NAME READY STATUS RESTARTS AGE nginx-84748895c4-k6bzl 1/1 Running 0 25s Whatshould you do to delete the deployment and avoid pod getting recreated?
A. kubectl delete deployment nginx
B. kubectl delete –deployment=nginx
C. kubectl delete pod nginx-84748895c4-k6bzl –no-restart 2
D. kubectl delete inginx
3. You are enhancing a production application currently running on an Ubuntu Linux VM onGoogle Compute Engine. The new enhancements require a connection to Cloud SQL to persistuser addresses. Your colleague has created the Cloud SQL instance and an IAM service accountwith the correct permissions but doesn’t know how to con􀃕gure the VM to use this serviceaccount, and has asked for your assistance. What should you do?
A. Execute gcloud iam service-accounts keys create to generate a ISON key for the serviceaccount. Add a metadata tag on the GCP project with key: service-account and value: .
B. Set the service account in the Identity and API access section when provisioning the
compute engine VM.
C. Execute gcloud iam service-accounts keys create to generate a JSON key for the serviceaccount. Add a metadata tag to the compute instance with key: service- account and value:
D. Execute gcloud iam service-accounts keys create to generate a JSON key for the serviceaccount. Copy the contents of JSON key to ~/identity/default-service- account.json overwritethe default service account.
30. You created a cluster.YAML 􀃕le containing : resources: – name: cluster type:container.vl.cluster properties: zone: europe-west1-b cluster: 2 description: “My GCP ACE cluster”# initialNodeCount: 2 You want to use Cloud Deployment Manager to create this cluster in GKE.What should you do?
A. gcloud deployment-manager deployments create my-gcp-ace-cluster –con􀃕gcluster.yaml
B. gcloud deployment-manager deployments apply my-gcp-ace-cluster_-typecontainer.v1.duster–con􀃕g cluster.yaml
C. gcloud deployment-manager deployments apply my-gcp-oce-cluster–con􀃕g cluster.yaml
D. gcloud deployment-manager deployments create my-gcp-ace-cluster–typecontainer.v1.cluster–con􀃕g cluster.yaml

31. Your company, which runs highly rated mobile games, has chosen to migrate its analyticsbackend to BigQuery. The analytics team of 7 analysts need access to perform queries against thedata in BigQuery. The analytics team members change frequently. How should you grant themaccess?
A. Create a Cloud Identity account for each analyst and grant roles/bigquery.dataViewelrole to each account.
B. Create a Cloud Identity account for each analyst and add them all to a group. Grantroles/bigquery.jobUser role to the group.
C. Create a Cloud Identity account for each analyst and add them all to a group. Grantroles/bigquery.dataViewer role to the group.
D. Create a Cloud Identity account for each analyst and grant roles/bigquery.jobUser role toeach account.

32. Your company plans to store sensitive PII data in a cloud storage bucket. Your compliancedepartment doesn’t like encrypting sensitive PII data with Google- managed keys and has askedyou to ensure the new objects uploaded to this bucket are encrypted by customer-managedencryption keys. What should you do?(Select Three)
A. In the bucket advanced settings, select the Customer-supplied key and then select aCloud KMS encryption key.
B. Use gsutil with –encryption-key=[ENCRYPTION_KEY] when uploading objects to thebucket.
C. In the bucket advanced settings, select the Customer-managed key and then select aCloud KMS encryption key.
D. Modify .boto con􀃕guration to include encryption_key = [KEY_RESOURCE] when uploadingobjects to bucket.
E. Use gsutil with -O “GSUtil:encryption_key=[KEY_RESOURCE]’ when uploading objects tothe bucket.
33. Your company recently acquired a startup that lets its developers pay for their projects usingtheir company credit cards. You want to consolidate the billing of all GCP projects into a newbilling account. You want to follow Google recommended practices. How should you do this?
A. Send an email to billing.support@cloud.google.con and request them to create a newbilling account and link all the projects to the billing account.
B. Raise a support request with Google Billing Support and request them to create a newbilling account and link all the projects to the billing account.
C. In the GCP Console, move all projects to the root organization in the Resource Manager.
D. Ensure you have the Billing Account Creator Role. Create a new Billing account yourselfand set up a payment method with company credit card details.
34. You are enhancing a production application currently running on an Ubuntu Linux VM onGoogle Compute Engine. The new enhancements require a connection to SQL Server instance topersist user appointments. Your colleague has provisioned an SQL Server instance in a GoogleCompute Engine VM in US-Central region and has asked for your assistance to RDP to the VM inthe least number of steps. What should you suggest?
A. Add a 􀃕rewall rule to allow TCP tra􀃞c on port 3389. In the GCP console, add a usernameand password for the Windows VM instance. Install Chrome RDP for Google Cloud Platformextension and click the RDP button in the console to connect to the instance with thecredentials.
B. In the GCP console, add a username and password for the Windows 0 VM instance.Install an RDP client and connect to the instance with username and password.
C. Add a 􀃕rewall rule to allow TCP tra􀃞c on port 3389. Install an RDP client and connect tothe instance.
D. Add a 􀃕rewall rule to allow TCP tra􀃞c on port 22. In the GCP console, add a password forthe Windows VM instance. Install Chrome RDP for Google Cloud Platform extension andclick the RDP button in the console to connect to the instance with the credentials.
36. You have two compute instances in the same VPC but in di􀃠erent regions. You can SSH fromone instance to another instance using their external IP address but not their internal IP address.What could be the reason for SSH failing on the internal IP address?
A. The compute instances have a static IP for their internal IP.
B. The combination of compute instance network tags and VPC 􀃕rewall rules allow SSHfrom 0.0.0.0 but denies SSH from the VPC subnets IP range.
C. The internal IP address is disabled.
D. The compute instances are not using the right cross-region SSH IAM permissions.
37. Your team is responsible for the migration of all legacy on-premises applications to GoogleCloud. Your team is a big admirer of serverless and has chosen App Engine Standard as thepreferred choice for compute workloads. Your manager asked you to migrate a legacy accountingapplication built in C++, but you realized App Engine Standard doesn’t support C++. What GCPcompute services should you use instead to maintain the serverless aspect?(Choose two answers)
A. Deploy the containerized version of the application in Cloud Run.
B. Deploy the containerized version of the application in Cloud Run on GKE.
C. Deploy the containerized version of the application in Google Kubernetes Engine (GKE).
D. Deploy the containerized version of the application in App Engine Flex.
E. Convert the application into a set of functions and deploy them in Google CloudFunctions.

38. Your company runs several internal applications on bare metal Kubernetes servers in youron-premises data centre. One of the applications deployed in the Kubernetes cluster uses a NASshare to save 􀃕les. In preparation for the upcoming migration to Google Cloud, you want toupdate the application to use Google Cloud Storage instead; however, security policies preventvirtual machines from having public IP addresses. What should you do?
A. Con􀃕gure a VPN tunnel between the on-premises data centre and the GCP VPC. Create acustom route in the VPC for Google Restricted APIs IP range (199.36.153.4/30) andpropagate the route over VPN. Resolve *.googleapis.com as a CNAME record torestricted.googleapis.com in your on-premises DNS server.
B. Make an exception and assign public IP addresses to the servers. Con􀃕gure 􀃕rewall rulesto allow tra􀃞c from the VM public IP addresses to the IP range of Cloud Storage.
C. Create a new VPC in GCP and deploy a proxy server like HAProxy/Squid to forwardrequests to Cloud Storage. Con􀃕gure a VPN tunnel between the on- premises data centre
and the GCP VPC. Have the servers access Cloud Storage through the proxy.
D. Migrate all VMs from the data centre to Google Compute Engine. Set up a Load Balanceron the GCP bucket and have the servers access Cloud Storage through the load balancer.
39. You want to persist logs for 10 years to comply with regulatory requirements. You want tofollow Google recommended practices. Which Google Cloud Storage class should you use?
A. Coldline storage class
B. Archive storage class
C. Nearline storage class
D. Standard storage class
4. A GKE cluster (test environment) in your test GCP project is experiencing issues with a sidecarcontainer connecting to Cloud SQL. This issue has resulted in a massive amount of log entries inCloud Logging and shot up your bill by 25%. Your manager has asked you to disable these logs asquickly as possible and using the least number of steps. You want to follow Google recommendedpractices. What should you do?
A. In Cloud Logging, disable the log source for GKE Cluster Operations resource in the Logsingestion window.
B. Recreate the GKE cluster and disable Cloud Logging.
C. Recreate the GKE cluster and disable Cloud Monitoring.
D. In Cloud Logging, disable the log source for GKE container resource in the Logs ingestionwindow.
40. You are in the process of migrating a mission-critical application from your on- premises datacentre to Google Kubernetes Engine (GKE). Your operations team do not want to take on theoverhead for upgrading the GKE cluster and have asked you to ensure the Kubernetes version isalways stable and supported. What should you do?
A. When provisioning the GKE cluster, ensure you use the latest stable and supportedversion.
B. Update your GKE cluster to turn on GKE’s node auto-upgrade feature.
C. When provisioning the GKE cluster, use Container Optimized os node images.
D. Update your GKE cluster to turn on GKE’s node auto-repair feature.
41. You have two workloads on GKE (Google Kubernetes Engine) – create-order and dispatch-order. create-order handles the creation of customer orders, and dispatch- order handlesdispatching orders to your shipping partner. Both create-order and dispatch-order workloadshave cluster autoscaling enabled. The create-order deployment needs to access (i.e. invoke webservice of) dispatch-order deployment. dispatch-order deployment cannot be exposed publicly.How should you de􀃕ne the services?
A. Create a Service of type ClusterlP for dispatch-order. Have create- order use the ServiceIP address.
B. Create a Service of type LoadBalancer for dispatch-order and an Ingress S Resource forthat Service. Have create-order use the Ingress IP address.
C. Create a Service of type LoadBalancer for dispatch-order. Have create-order use theService IP address.
D. Create a Service of type NodePort for dispatch-order and an Ingress Resource for thatService. Have create-order use the Ingress IP address.
42. Your company runs a very successful web platform and has accumulated 3 petabytes ofcustomer activity data in sharded MySQL database located in your datacenter. Due to storagelimitations in your on-premise data center, your company has decided to move this data to GCP.The data must be available all through the day. Your business analysts, who have experience ofusing a SQL Interface, have asked for a seamless transition. How should you store the data sothat availability is ensured while optimizing the ease of analysis for the business analysts?
A. Import data into Google BigQuery.
B. Import 􀃖at 􀃕les into Google Cloud Storage.
C. Import data into Google Cloud Datastore.
D. Import data into Google Cloud SQL
43. Your manager asked you to write a script to upload objects to a Cloud Storage bucket. Howshould you set up the IAM access to enable the script running in a Google Compute VM uploadobjects to Cloud Storage?
A. Create a new IAM service account with the access scope cloud-platform and con􀃕gurethe script to use this service account.
B. Grant roles/storage.objectCreator IAM role to the service account used by the VM.
C. Grant roles/storage.objectAdmin IAM role to the service account used by the VM.
D. Create a new IAM service account with the access scope devstorage.write_only andcon􀃕gure the script to use this service account
44. You are migrating your on-premises workloads to GCP VPC, and you want to use ComputeEngine virtual machines. You want to separate the Finance team VMs and the Procurement teamVMs into separate subnets. You need all VMs to communicate with each other over their internalIP addresses without adding routes. What should you do?
A. Use Deployment Manager to create a new VPC with 2 subnets in 2 di􀃠erent regions.Ensure the subnets use non-overlapping IP range.
B. Use Deployment Manager to create a new VPC with 2 subnets in the same region. Ensurethe subnets use the same IP range.
C. Use Deployment Manager to create two VPCs, each with a subnet in a di􀃠erent region.Ensure the subnets use non-overlapping IP range.
D. Use Deployment Manager to create two VPCs, each with a subnet in the same 0 region.Ensure the subnets use overlapping IP range.
45. Your compliance team requested all audit logs are stored for 10 years and to allow access forexternal auditors to view. You want to follow Google recommended practices. What should youdo?(Choose two)
A. Create an account for auditors to have view access to Stackdriver Logging.
B. Export audit logs to Cloud Storage via an export sink.
C. Export audit logs to Splunk via a Pub/Sub export sink.
D. Generate a signed URL to the Stackdriver export destination for auditors to access.
E. Export audit logs to BigQuery via an export sink.
46. Your company plans to migrate all applications from its on-premises data centre to GoogleCloud Platform. The DevOps team currently use Jenkins extensively to automate con􀃕gurationupdates in applications. How should you provision Jenkins in Google Cloud with the least numberof steps?
A. Download Jenkins binary from https://www.jenkins.io/download/ and deploy in GoogleApp Engine Standard Service.
B. Create a Kubernetes Deployment YAML 􀃕le referencing the Jenkins docker image anddeploy to a new GKE cluster.
C. Download Jenkins binary from https://www.jenkins.io/download/ and deploy in a newGoogle Compute Engine instance.
D. Provision Jenkins from GCP marketplace.
47. You have a number of compute instances belonging to an unmanaged instances group. Youneed to SSH to one of the Compute Engine instances to run an ad hoc script. You’ve alreadyauthenticated gcloud, however, you don’t have an SSH key deployed yet. In the fewest stepspossible, what’s the easiest way to SSH to the instance?
A. Run gcloud compute instances list to get the IP address of the instance, then use the sshcommand.
B. Use the gcloud compute ssh command.
C. Create a key with the ssh-keygen command. Then use the gcloud compute sshcommand.
D. Create a key with the ssh-keygen command. Upload the key to the instance. Run gcloudcompute instances list to get the IP address of the instance, then use the ssh command.
48. Your compliance department has asked you to share a compressed zip of sensitive audit logswith an external auditor. The external auditor does not have a Google account, and you want to
remove the access after 4 hours. How can you do this securely with the least number of steps?
A. Con􀃕gure Static Website hosting on the Cloud Storage bucket, make the zip 􀃕le publicand ask the auditor to download the 􀃕le from the website.
B. Delete the zip 􀃕le after 4 hours. Copy the zip 􀃕le to a new Cloud Storage bucket, makethe bucket public and share the URL securely with the external auditor.
C. Delete the new bucket after 4 hours. Use gcloud to generate a signed URL on the objectwith a four-hour expiry. Securely share the URL with the external auditor.
D. Make the zip 􀃕le public and securely share the URL with the external auditor. Set up alifecycle policy to delete the object after 4 hours.
49. You have three gcloud con􀃕gurations – one for each of development, test and productionprojects. You want to list all the con􀃕gurations and switch to a new con􀃕guration. With the feweststeps possible, what’s the fastest way to switch to the correct con􀃕guration?
A. To list con􀃕gurations gcloud con􀃕g con􀃕gurations list To activate a con􀃕guration – gcloudcon􀃕g con􀃕gurations activate.
B. To list con􀃕gurations gcloud con􀃕g list To activate a con􀃕guration – gcloud con􀃕gactivate.
C. To list con􀃕gurations – gcloud con􀃕gurations list To activate a con􀃕guration gcloud con􀃕gactivate.
D. To list con􀃕gurations – gcloud con􀃕gurations list To activate a con􀃕guration goloudcon􀃕gurations activate
50. You are exploring the possibility of migrating a mission-critical application from your on-premises data centre to Google Cloud Platform. You want to host this on a GKE cluster withautoscaling enabled, and you need to ensure each node can run a pod to push the applicationlogs to a third-party logging platform. How should you deploy the pod?
A. Initialize the logging pod during the GKE Cluster creation.
B. Add the logging pod in the Deployment YAML 􀃕le.
C. Deploy the logging pod in a DaemonSet Kubernetes object.
D. Deploy the logging pod in a StatefulSet Kubernetes object.
6. You are developing a simple application in App Engine Standard service. Unit testing and useracceptance testing has succeeded, and you want to build a new App Engine application to serveas your performance testing environment. What should you do?
A. Use gcloud to deploy the application to a new performance testing GCP project byspecifying the –project parameter. Select Yes when prompted for con􀃕rmation on creatinga new project.
B. Create a new GCP project for the performance testing environment using gcloud anddeploy your App Engine application to the new GCP project.
C. Con􀃕gure a Deployment Manager YAML template to copy the application from thedevelopment GCP project into the performance testing GCP project.
D. Create a new GCP project for the performance testing environment using gcloud andcopy the application from the development GCP project into the performance testing GCPproject.
7. Your company has a number of GCP projects that are managed by the respective projectteams. Your expenditure of all GCP projects combined has exceeded your operationalexpenditure budget. At a review meeting, it has been agreed that your 􀃕nance team should beable to set budgets and view the current charges for all projects in the organization but not viewthe project resources; and your developers should be able to see the Google Cloud Platformbilling charges for only their own projects as well as view resources within the project. You wantto follow Google recommended practices to set up IAM roles and permissions. What should youdo?
A. Add the 􀃕nance team to the Billing Account Administrator role for each of the billingaccounts that they need to manage. Add the developers to the Viewer role for the Project.
B. Add the 􀃕nance team to the Viewer role for the Project.Add the developers to theSecurity Reviewer role for each of the billing accounts.
4/3/2021 Google Associate Cloud Engineer Practice Exam Part 4
https://gcp-examquestions.com/google-associate-cloud-engineer-practice-exam-part-4/ 18/22
C. Add the 􀃕nance team to the default IAM Owner role. Add the developers to a customrole that allows them to see their own spend only.
D. Add the developers and 􀃕nance managers to the Viewer role for the Project.
8. Your team manages the game backend for a popular game with users all over the world. Thegame backend APIs runs on a 􀃖eet of VMs behind a Managed Instance Group (MIG) withautoscaling enabled. You have con􀃕gured the scaling policy on the MIG to add more instances ifthe CPU utilization is consistently over 85%, and to scale down when the CPU utilization isconsistently lower than 65%. You noticed the autoscaler adds more VMs than is necessary duringthe scale-up, and you suspect this might be down to an incorrect con􀃕guration in the healthcheck – the initial delay on the health check is 30 seconds. Each VM takes just under 3 minutesbefore it is ready to process the requests from the web application and mobile app. What shouldyou do to 􀃕x the scaling issue?
A. Update the Managed Instances template to set the maximum instances to 5.
B. Update the Managed Instances template to set the maximum instances to 1.
C. Update the autoscaling health check from HTTP to TCP.
D. Update the autoscaling health check to increase the initial delay to 200 seconds.
9. You are the Cloud Security Manager at your company, and you want to review IAM users andtheir assigned roles in the production GCP project. You want to follow Google recommendedpractices. What should you do?
A. Review the information in the Roles section for the production GCP project in GoogleCloud Console.
B. Check the output of gcloud iam roles list command.
C. Check the output of gcloud iam service-accounts list command.
D. Review the information in the IAM section for the production GCP project in GoogleCloud Console.
