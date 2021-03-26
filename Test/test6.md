# Exam 1

1. You are a project owner and need your co-worker to deploy a new version of your application to App Engine. You want to follow Google’s recommended practices. Which IAM roles should you grant your co-worker?

    * A. Project Editor
    * B. App Engine Service Admin
    * **C. App Engine Deployer**
    * D. App Engine Code Viewer

2. Your company has reserved a monthly budget for your project. You want to be informed automatically of your project spend so that you can take action when you approach the limit. What should you do?

    * A. Link a credit card with a monthly limit equal to your budget.
    * B. **Create a budget alert for 50%, 90%, and 100% of your total monthly budget.**
    * C. In App Engine Settings, set a daily budget at the rate of 1/30 of your monthly budget.
    * D. In the GCP Console, configure billing export to BigQuery. Create a saved view that queries your total spend.

3. You have a project using BigQuery. You want to list all BigQuery jobs for that project. You want to *set this project* as the default for the bq command-line tool. What should you do?

    * A. **Use “gcloud config set project” to set the default project.**
    * B. Use “bq config set project” to set the default project.
    * C. Use “gcloud generate config-url” to generate a URL to the Google Cloud Platform Console to set the default project.
    * D. Use “bq generate config-url” to generate a URL to the Google Cloud Platform Console to set the default project.

4. Your project has all its Compute Engine resources in the europe-west1 region. You want to set europe-west1 as the default region for gcloud commands. What should you do?

    * A. Use Cloud Shell instead of the command line interface of your device. Launch Cloud Shell after you navigate to a resource in the europe-west1 region. The europe-west1 region will automatically become the default region.
    * B. **Use “gcloud config set compute/region europe-west1” to set the default region for future gcloud commands.**
    * C. Use “gcloud config set compute/zone europe-west1” to set the default region for future gcloud commands.
    * D. Create a VPN from on-premises to a subnet in europe-west1, and use that connection whenexecuting gcloud commands.

5. You developed a new application for App Engine and are ready to deploy it to production. You need to estimate the costs of running your application on Google Cloud Platform as accurately as possible.What should you do?

    * A. Create a YAML file with the expected usage. Pass this file to the “gcloud app estimate” command toget an accurate estimation.
    * B. Multiply the costs of your application when it was in development by the number of expected usersto get an accurate estimation.
    * **C. Use the pricing calculator for App Engine to get an accurate estimation of the expected charges.**
    * D. Create a ticket with Google Cloud Billing Support to get an accurate estimation.

6. Your company processes high volumes of IoT data that are time-stamped. The total data volume can be several petabytes. The data needs to be written and changed at a high speed. You want to use the most performant storage option for your data. Which product should you use?

    * A. Cloud Datastore
    * B. Cloud Storage
    * C. **Cloud Bigtable**
    * D. BigQuery

7. Your application has a large international audience and runs stateless virtual machines within a managed instance group across multiple locations. One feature of the application lets users upload files and share them with other users. Files must be available for 30 days; after that, they are removed from the system entirely. Which storage solution should you choose?

    * A. A Cloud Datastore database.
    * B. **A multi-regional Cloud Storage bucket.**
    * C. Persistent SSD on virtual machine instances.
    * D. A managed instance group of Filestore servers.

8. You have a definition for an instance template that contains a web application. You are asked to deploy the application so that it can scale based on the HTTP traffic it receives. What should you do?

    * A. Create a VM from the instance template. Create a custom image from the VM’s disk. Export the image to Cloud Storage. Create an HTTP load balancer and add the Cloud Storage bucket as its backend service.
    * B. Create a VM from the instance template. Create an App Engine application in Automatic Scaling mode that forwards all traffic to the VM.
    * C. **Create a managed instance group based on the instance template. Configure autoscaling based on HTTP traffic and configure the instance group as the backend service of an HTTP load balancer.**
    * D. Create the necessary amount of instances required for peak user traffic based on the instance template. Create an unmanaged instance group and add the instances to that instance group.Configure the instance group as the Backend Service of an HTTP load balancer.

9. You are creating a Kubernetes Engine cluster to deploy multiple pods inside the cluster. All container logs must be stored in BigQuery for later analysis. You want to follow Google-recommended practices. Which two approaches can you take?

    * A. **Turn on Stackdriver Logging during the Kubernetes Engine cluster creation.**
    * B. Turn on Stackdriver Monitoring during the Kubernetes Engine cluster creation.
    * C. Develop a custom add-on that uses Cloud Logging API and BigQuery API. Deploy the add-on to your Kubernetes Engine cluster.
    * D. **Use the Stackdriver Logging export feature to create a sink to Cloud Storage. Create a Cloud Dataflow job that imports log files from Cloud Storage to BigQuery.**
    * E. Use the Stackdriver Logging export feature to create a sink to BigQuery. Specify a filter expression to export log records related to your Kubernetes Engine cluster only.

10. You need to create a new Kubernetes Cluster on Google Cloud Platform that can autoscale the number of worker nodes. What should you do?

    * A. **Create a cluster on Kubernetes Engine and enable autoscaling on Kubernetes Engine.**
    * B. Create a cluster on Kubernetes Engine and enable autoscaling on the instance group of the cluster.
    * C. Configure a Compute Engine instance as a worker and add it to an unmanaged instance group. Add a load balancer to the instance group and rely on the load balancer to create additional ComputeEngine instances when needed.
    * D. Create Compute Engine instances for the workers and the master, and install Kubernetes. Rely on Kubernetes to create additional Compute Engine instances when needed.

11. Your company has a mission-critical application that serves users globally. You need to select a transactional, relational data storage system for this application. Which two products should you consider

    * A. BigQuery
    * B. **Cloud SQL**
    * C. Cloud Spanner
    * D. **Cloud Bigtable**
    * E. Cloud Datastore

12. You have a Kubernetes cluster with 1 node-pool. The cluster receives a lot of trafficc and needs to grow. You decide to add a node. What should you do?

    * A. **Use “gcloud container clusters resize” with the desired number of nodes.**
    * B. Use “kubectl container clusters resize” with the desired number of nodes.
    * C. Edit the managed instance group of the cluster and increase the number of VMs by 1.
    * D. Edit the managed instance group of the cluster and enable autoscaling.

13. You created an update for your application on App Engine. You want to deploy the update without impacting your users. You want to be able to roll back as quickly as possible if it fails. What should youdo?

    * A. Delete the current version of your application. Deploy the update using the same version identiferas the deleted version.
    * B. Notify your users of an upcoming maintenance window. Deploy the update in that maintenance window.
    * C. Deploy the update as the same version that is currently running.
    * D. **Deploy the update as a new version. Migrate trafficc from the current version to the new version.**

14. You have created a Kubernetes deployment, called Deployment-A, with 3 replicas on your cluster. Another deployment, called Deployment-B, needs access to Deployment-A. You cannot expose Deployment-A outside of the cluster. What should you do?

    * A. Create a Service of type NodePort for Deployment A and an Ingress Resource for that Service. Have Deployment B use the Ingress IP address.
    * B. Create a Service of type LoadBalancer for Deployment A. Have Deployment B use the Service IPaddress.
    * C. **Create a Service of type LoadBalancer for Deployment A and an Ingress Resource for that Service.Have Deployment B use the Ingress IP address.**
    * D. Create a Service of type ClusterIP for Deployment A. Have Deployment B use the Service IP address.

15. You need to estimate the annual cost of running a Bigquery query that is scheduled to run nightly.What should you do?

    * A. Use “gcloud query –dry_run” to determine the number of bytes read by the query. Use this numberin the Pricing Calculator.
    * B. **Use “bq query –dry_run” to determine the number of bytes read by the query. Use this number inthe Pricing Calculator.**
    * C. Use “gcloud estimate” to determine the amount billed for a single query. Multiply this amount by365.
    * D. Use “bq estimate” to determine the amount billed for a single query. Multiply this amount by 365.

16. You want to find out who in your organization has Owner access to a project called "my-project".What should you do?

    * A. **In the Google Cloud Platform Console, go to the IAM page for your organization and apply the filter“Role:Owner”.**
    * B. In the Google Cloud Platform Console, go to the IAM page for your project and apply the filter“Role:Owner”.
    * C. Use “gcloud iam list-grantable-role –project my-project” from your Terminal.
    * D. Use “gcloud iam list-grantable-role” from Cloud Shell on the project page.

17. You want to create a new role for your colleagues that will apply to all current and future projects created in your organization. The role should have the permissions of the BigQuery Job User and Cloud Bigtable User roles. You want to follow Google’s recommended practices. How should you create the new role?

    * A. Use "gcloud iam combine-roles –global" to combine the 2 roles into a new custom role.
    * B. For one of your projects, in the Google Cloud Platform Console under Roles, select both roles and combine them into a new custom role. Use “gcloud iam promote-role” to promote the role from aproject role to an organization role.
    * C. **For all projects, in the Google Cloud Platform Console under Roles, select both roles and combine them into a new custom role**.
    * D. For your organization, in the Google Cloud Platform Console under Roles, select both roles and combine them into a new custom role.

18. You work in a small company where everyone should be able to view all resources of a specific project. You want to grant them access following Google’s recommended practices. What should you do?

    * A. Create a script that uses “gcloud projects add-iam-policy-binding” for all users’ email addresses andthe Project Viewer role.
    * B. A. Create a script that uses “gcloud iam roles create” for all users’ email addresses and the Project Viewer role.
    * C. **Create a new Google Group and add all users to the group. Use “gcloud projects add-iam-policy-binding” with the Project Viewer role and Group email address.**
    * D. Create a new Google Group and add all members to the group. Use “gcloud iam roles create” withthe Project Viewer role and Group email address.

19. You need to verify the assigned permissions in a custom IAM role. What should you do?

    * **A. Use the GCP Console, IAM section to view the information.**
    * B. Use the “gcloud init” command to view the information.
    * C. Use the GCP Console, Security section to view the information.
    * D. Use the GCP Console, API section to view the information.

20. Which of the following services provides real-time messaging?

    * A. **Cloud Pub/Sub**
    * B. Big Query
    * C. App Engine
    * D. Datastore

21. Which of the following tasks would Nearline Storage be well suited for?

    * A. A mounted Linux file system
    * B. Image assets for a high traffic website
    * C. Frequently read files
    * D. **Infrequently read data backups**

22. Which of the following products will allow you to administer your projects through a browser based command-line?

    * A. Cloud Datastore
    * B. Cloud Command-line
    * C. **Cloud Terminal**

23. Cloud SQL is based on which database engine?

    * A. Microsoft SQL Server
    * B. **MySQL**
    * C. Oracle
    * D. Informix

24. Which of the following products will allow you to perform live debugging without stopping your application?

    * A. App Engine Active Debugger (AEAD)
    * B. **Stackdriver Debugger**
    * C. Code Inspector
    * D. Pause IT

25. Which of these options is not a valid Cloud Storage class?

    * A. **Glacier Storage**
    * B. Nearline Storage
    * C. Coldline Storage
    * D. **Regional Storage**

26. Regarding Cloud Storage, which option allows any user to access to a Cloud Storage resource for a limited time, __using a specific URL__?

    * A. Open Buckets
    * B. Temporary Resources
    * C. **Signed URLs**
    * D. Temporary URLs

27. Of the options given, which is a NoSQL database?

    * A. **Cloud Datastore**
    * B. Cloud SQL
    * C. All of the given options
    * D. Cloud Storage

28. Container Engine allows orchastration of what type of containers?

    * A. Blue Whale
    * B. LXC
    * C. BSD Jails
    * D. **Docker**

29. Regarding Cloud IAM, what type of role(s) are available?

    * A. Basic roles and Compiled roles
    * B. **Primitive roles and Predefined roles**
    * C. Simple roles
    * D. Basic roles and Curated roles

30. Which of the follow products will allow you to host a static website?

    * A. Cloud SDK
    * B. Cloud Endpoints
    * C. **Cloud Storage**
    * D. Cloud Datastore

31. Container Engine is built on which open source system?

    * A. Swarm
    * B. Kubernetes
    * C. **Docker Orchastrate**
    * D. Mesos

32. Cloud Source Repositories provide a hosted version of which version control system?

    * A. **Git**
    * B. RCS
    * C. SVN
    * D. Mercurial

33. Which of the following is an analytics data warehouse?

    * A. Cloud SQL
    * B. **BigQuery**
    * C. Datastore
    * D. Cloud Storage

34. Which service offers the ability to create and run virtual machines?

    * A. Google Virtualization Engine
    * B. Compute Containers
    * C. VM Engine
    * D. **Compute Engine**

35. Which of the following is not helpful for mitigating the impact of an unexpected failure or reboot?

    * A. Use persistent disks
    * B. Configure tags and labels
    * C. **Use startup scripts to re-configure the system as needed**
    * D. Backup your data

36. Which tool allows you to sync data in your Google domain with Active Directory?

    * A. **Google Cloud Directory Sync (GCDS)**
    * B. Google Active Directory (GAD)
    * C. Google Domain Sync Service
    * D. Google LDAP Sync

37. Regarding Cloud Storage: which of the following allows for time-limited access to buckets and objects without a Google account?

    * A. Signed URLs
    * B. gsutil
    * C. Single sign-on
    * D. Temporary Storage Accounts

38. Which of the following is a virtual machine instance that can be terminated by Compute Engine without warning?

    * A. **A preemptible VM**
    * B. A shared-core VM
    * C. A high-cpu VM
    * D. A standard VM

39. Regarding Compute Engine: What is a managed instance group?

    * A. **A managed instance group combines existing instances of diferent configurations into one manageable group**
    * B. A managed instance group uses an instance template to create identical instances
    * C. A managed instance group creates a  firewall around instances
    * D. A managed instance group is a set of servers used exclusively for batch processing

40. What type of firewall rule(s) does Google Cloud’s networking support?

    * A. deny
    * B. allow, deny & filtered
    * C. allow
    * D. **allow & deny**

41. How are subnetworks diferent than the legacy networks?

    * A. They’re the same, only the branding is diferent
    * B. Each subnetwork controls the IP address range used for instances that are allocated to that subnetwork
    * C. With subnetworks IP address allocation occurs at the global network level
    * D. Legacy networks are the preferred way to create networks

42. Which of the following __is not a valid metric for triggering autoscaling__?

    * A. Google Cloud Pub/Sub queuing
    * B. **Average CPU utilization**
    * C. Stackdriver Monitoring metrics
    * D. App Engine Task Queues

43. Which of the following features makes applying firewall settings easier?

    * A. Service accounts
    * B. **Tags**
    * C. Metadata
    * D. Labels

44. What option does Cloud SQL offer to help with high availability?

    * A. Point-in-time recovery
    * B. The Always On setting
    * C. Snapshots
    * D. **Failover replicas**

45. Regarding Compute Engine: when executing a __startup script on a Linux server__ which user does theinstance execute the script as?

    * A. **ubuntu**
    * B. The Google provided “gceinstance” user
    * C. Whatever user you specify in the console
    * D. root

46. Which of the follow methods will not cause a shutdown script to be executed?

    * A. When an instance shuts down through a request to the guest operating system
    * B. **A preemptible instance being terminated**
    * C. An instances.reset API call
    * D. Shutting down via the cloud console

47. Which type of account would you use in code when you want to interact with Google Cloud Services?

    * A. Google group
    * B. Service account
    * C. Code account
    * D. Google account

48. Which of the following is not an IAM best practice?

    * A. **Use primitive roles by default**
    * B. Treat each component of your application as a separate trust boundary
    * C. Grant roles at the smallest scope needed
    * D. Restrict who has access to create and manage service accounts in your project

49. Which of the following would not reduce your recovery time in the event of a disaster?

    * A. Make it as easy as possible to adjust the DNS record to cut over to your warm standby server.
    * B. Replace your warm standby server with a hot standby server.
    * C. Use a highly preconfigured machine image for deploying new instances.
    * D. Replace your active/active hybrid production environment (on-premises and GCP) with a warmstandby server.

50. Which of the following is not a best practice for mitigating Denial of Service attacks on your Google Cloud infrastructure?

    * A. Block SYN foods using Cloud Router
    * B. Isolate your internal traffc from the external world
    * C. Scale to absorb the attack
    * D. Reduce the attack surface for your GCE deployment

51. Which is the fastest instance storage option that will still be available when an instance is stopped?

    * A. Local SSD
    * B. Standard Persistent Disk
    * C. SSD Persistent Disk
    * D. RAM disk

52. Which of these statements about Microsoft licenses is true?
 
    * A. You can migrate your existing Microsoft application licenses to Compute Engine instances, but not your Microsoft Windows licenses.
    * B. You can migrate your existing Microsoft Windows and Microsoft application licenses to Compute Engine instances.
    * C. You cannot migrate your existing Microsoft Windows or Microsoft application licenses to Compute Engine instances.
    * D. You can migrate your existing Microsoft Windows licenses to Compute Engine instances, but not your Microsoft application licenses.

53. Which database services support standard SQL queries?

    * A. Cloud Bigtable and Cloud SQL
    * B. **Cloud Spanner and Cloud SQL**
    * C. Cloud SQL and Cloud Datastore
    * D. Cloud SQL

54. Which statement about IP addresses is false?

    * A. You are charged for a static external IP address for every hour it is in use.
    * B. You are not charged for ephemeral IP addresses.
    * C. **Google Cloud Engine supports only IPv4 addresses, not IPv6.**
    * D. You are charged for a static external IP address when it is assigned but unused.

55. Which Google Cloud Platform service requires the least management because it takes care of theunderlying infrastructure for you?

    * A. Container Engine
    * B. Cloud Engine
    * C. **App Engine**
    * D. Docker containers running on Cloud Engine

56. To ensure that your application will handle the load even if an entire zone fails, what should you do?

    * A. Don’t select the “Multizone” option when creating your managed instance group.
    * B. Spread your managed instance group over two zones and overprovision by 100%.
    * C. Create a regional unmanaged instance group and spread your instances across multiple zones.
    * D. Overprovision your regional managed instance group by at least 50%.

57. If you do not grant a user named Bob permission to access a Cloud Storage bucket, but then usean ACL to grant access to an object inside that bucket to Bob, what will happen?

    * A. Bob will be able to access all of the objects inside the bucket because he was granted access to at least one object in the bucket.
    * B. Bob will be able to access the object because bucket and object ACLs are independent of eachother.
    * C. Bob will not be able to access the object because he does not have access to the bucket.
    * D. **It is not possible to grant access to an object when it is inside a bucket for which a user does not have access.**

58. To set up a virtual private network between your office network and Google Cloud Platform and have the routes automatically updated when the network topology changes, what is the minimal number of each type of component you need to implement?

    * A. 2 Cloud VPN Gateways and 1 Peer Gateway
    * B. 1 Cloud VPN Gateway, 1 Peer Gateway, and 1 Cloud Router
    * C. 2 Peer Gateways and 1 Cloud Router
    * D. 2 Cloud VPN Gateways and 1 Cloud Router

59. Which of the following statements about encryption on GCP is not true?

    * A. Google Cloud Platform encrypts customer data stored at rest by default.
    * B. Each encryption key is itself encrypted with a set of master keys.
    * C. If you want to manage your own encryption keys for data on Google Cloud Storage, the only optionis Customer-Managed Encryption Keys (CMEK) using Cloud KMS.
    * D. Data in Google Cloud Platform is broken into subfile chunks for storage, and each chunk is encrypted at the storage level with an individual encryption key.

60. Which database service requires that you configure a failover replica to make it highly available?

    * A. Cloud Spanner
    * B. **Cloud SQL**
    * C. BigQuery
    * D. Cloud Datastore

61. Which of these is not a principle you should apply when setting roles and permissions?

    * A. Whenever possible, assign roles to groups instead of to individuals.
    * B. Grant users the appropriate permissions to facilitate least privilege
    * C. **Whenever possible, assign primitive roles rather than predefined roles.**
    * D. Audit all policy changes by checking the Cloud Audit Logs.

62. Which of these is not a recommended method of authenticating an application with a GoogleCloud service?

    * A. Use the gcloud and/or gsutil commands.
    * B. **Request an OAuth2 access token and use it directly.**
    * C. Embed the service account’s credentials in the application’s source code.
    * D. Use one of the Google Cloud Client Libraries.

63. What are two diferent features that fully isolate groups of VM instances?

    * A. **Firewall rules and subnetworks**
    * B. Networks and subnetworks
    * C. Subnetworks and projects
    * D. Projects and networks

64. Suppose you have a web server that is working properly, but you can’t connect to its instance VMover SSH. Which of these troubleshooting methods can you use without disrupting production traffic?(Select 3 answers.)

    * A. **Create a snapshot of the disk and use it to create a new disk; then attach the new disk to a new instance**
    * B. Use netcat to try to connect to port 22
    * C. Access the serial console output
    * D. Create a startup script to collect information.

65. To configure Stackdriver to monitor a web server and let you know if it goes down, what steps do you need to take? (Select 2 answers.)

    * A. **Install the Stackdriver Logging Agent on the web server**
    * B. Create an alerting policy
    * C. **Install the Stackdriver Monitoring Agent on the web server**
    * D. Create an uptime check

66. Which of these tools can you use to copy data from AWS S3 to Cloud Storage? (Select 2 answers.)

    * A. **Cloud Storage Transfer Service**
    * B. **S3 Storage Transfer Service**
    * C. Cloud Storage Console
    * D. gsutil

67. What are two of the actions you can take to toubleshoot a virtual machine instance that won’t start up at all? (Select 2 answers.)

    * A. **Increase the CPU and memory on the instance by changing the machine type.**
    * B. Validate that your disk has a valid file system.
    * C. **Examine your virtual machine instance’s serial port output.**
    * D. Connect to your virtual machine instance using SSH.

68. Which statements about application load testing are true? (Select 2 answers.)

    * A. You should test at the maximum load that you expect to encounter.
    * B. You should test at 50% more than the maximum load that you expect to encounter.
    * C. It is not necessary to test sudden increases in traffic since GCP scales seamlessly.
    * D. Your load tests should include testing sudden increases in traffic.

69. Which of these statements about resilience testing are true? (Select 2 answers.)

    * A. In a resilience test, your application should keep running with little or no downtime.
    * B. To test the resilience of an autoscaling instance group, you can terminate a random instance withinthat group.
    * C. In order for an application to survive instance failures, it should not be stateless.
    * D. Resilience testing is the same as disaster recovery testing.

70. Which combination of Stackdriver services will alert you about errors generated by your applications and help you locate the root cause in the code?

    * A. Monitoring, Trace, and Debugger
    * B. Monitoring and Error Reporting
    * C. Debugger and Error Reporting
    * D. **Alerts and Debugger**

71. If you have configured Stackdriver Logging to export logs to BigQuery, but logs entries are not getting exported to BigQuery, what is the most likely cause?

    * A. The Cloud Data Transfer Service has not been enabled.
    * B. There isn’t a firewall rule allowing traffic between Stackdriver and BigQuery.
    * C. **Stackdriver Logging does not have permission to write to the BigQuery dataset.**
    * D. The size of the Stackdriver log entries being exported exceeds the maximum capacity of the BigQuery dataset.

72. You can use Stackdriver to monitor virtual machines on which cloud platforms?

    * A. Google Cloud Platform, Microsoft Azure
    * B. Google Cloud Platform
    * C. **Google Cloud Platform, Microsoft Azure, Amazon Web Services**
    * D. Google Cloud Platform, Amazon Web Services

73. To minimize the risk of someone changing your log files to hide their activities, which of the following principles would help? (Select 3 answers.)

    * A. **Restrict usage of the owner role for projects and log buckets.**
    * B. Require two people to inspect the logs.
    * C. **Implement object versioning on the log-buckets.**
    * D. **Encrypt the logs using Cloud KMS.**

74. If network traffic between one Google Compute Engine instance and another instance is beingdropped, what is the most likely cause?

    * A. The instances are on a network with low bandwidth.
    * B. The TCP keep-alive setting is too short.
    * C. The instances are on a default network with no additional firewall rules.
    * D. **A firewall rule was deleted.**

75. Which of the following practices can help you develop more secure software? (Select 3 answers.)

    * A. **Penetration tests**
    * B. **Integrating static code analysis tools into your CI/CD pipeline**
    * C. Encrypting your source code
    * D. **Peer review of code**

76. Which two places hold information you can use to monitor the effects of a Cloud Storage lifecycle policy on specific objects? (Select 2 answers.)

    * A. **Cloud Storage Lifecycle Monitoring**
    * B. **Expiration time metadata**
    * C. Access logs
    * D. Lifecycle config file

77. If you have object versioning enabled on a multi-regional bucket, what will the following lifecycle config file do?

    * A. Archive objects older than 30 days (the second rule doesn’t do anything)
    * B. Delete objects older than 30 days (the second rule doesn’t do anything)
    * C. Archive objects older than 30 days and move objects to Coldline Storage after 365 days
    * D. Delete objects older than 30 days and move objects to Coldline Storage after 365 days

78. Which of the following statements about Stackdriver Trace are true? (Select 2 answers.)

    * A. Stackdriver Trace tracks the performance of the virtual machines running the application.
    * B. Stackdriver Trace tracks the latency of incoming requests.
    * C. Applications in App Engine automatically submit traces to Stackdriver Trace. Applications outside ofApp Engine need to use the Trace SDK or Trace API.
    * D. To make an application work with Stackdriver Trace, you need to add instrumentation code using

79. You have been asked to select the storage system for the click-data of your company’s largeportfolio of websites. This data is streamed in from a custom website analytics package at a typicalrate of 6,000 clicks per minute. With bursts of up to 8,500 clicks per second. It must have been storedfor future analysis by your data science and user experience teams.
Which storage infrastructure should you choose?
A. Google Cloud SQL
B. Google Cloud Bigtable
C. Google Cloud Storage
D. Google Cloud Datastore
1. You want to optimize the performance of an accurate, real-time, weather-charting application. Thedata comes from 50,000 sensors sending 10 readings a second, in the format of a timestamp andsensor reading.
Where should you store the data?
A. Google BigQuery
B. Google Cloud SQL
C. Google Cloud Bigtable
D. Google Cloud Storage
1. You have been asked to select the storage system for the click-data of your company’s largeportfolio of websites. This data is streamed in from a custom website analytics package at a typicalrate of 6,000 clicks per minute. With bursts of up to 8,500 clicks per second. It must have been storedfor future analysis by your data science and user experience teams.
Which storage infrastructure should you choose?
A. Google Cloud SQL
B. Google Cloud Bigtable
C. Google Cloud Storage
D. Google Cloud Datastore
1. You want to optimize the performance of an accurate, real-time, weather-charting application. Thedata comes from 50,000 sensors sending 10 readings a second, in the format of a timestamp andsensor reading.
Where should you store the data?
A. Google BigQuery
B. Google Cloud SQL
C. Google Cloud Bigtable
D. Google Cloud Storage
