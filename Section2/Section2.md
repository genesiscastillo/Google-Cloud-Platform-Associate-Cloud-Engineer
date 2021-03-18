# 2.- Planning and configuring a cloud solution

## 2.1.- Planning and estimating GCP product use using the Pricing Calculator

* Video
    - [Google Cloud Platform on a shoestring budget](https://www.youtube.com/watch?v=N2OG1w6bGFo)
    - [Pricing Calculator](https://www.youtube.com/watch?v=gZidr8ztscw)
    - [Questions about Cost/Pricing](https://www.youtube.com/watch?v=fzW0ykVabpU)

* Doc References
    - [Link Key](https://cloud.google.com/products/calculator)
---
## 2.2.- Planning and configuring compute resources
---
### 2.2.1 - Selecting appropriate compute choices for a given workload

* Video
    - [Deciding between Compute Engine, Container Engine, App Engine and more](https://www.youtube.com/watch?v=g0dN8Hkh5H8)

#### 2.2.1.1 - Compute Engine
> And Compute Engine is, basically, kind of everything else, or even all of those things if you want. It's VM.
So you have full control to do whatever you need to do to connect things together.
It's also a really good fit for existing systems.

#### 2.2.1.2 - Kubernetes Engine
> Container Engine is a system of containers working together to solve your problems.

##### 2.2.1.3 - App Engine
> Video: [Get to know Google App Engine](https://www.youtube.com/watch?v=2PRciDpqpko)

> App Engine is focused on making your web code run extremely well.
It's optimized for that. And it's code first kind of thinking.

---
#### 2.2.2 - Using preemptible VMs and custom machine types as appropriate
* [Command references](https://cloud.google.com/sdk/gcloud/reference/compute/instances/create?hl=es)
* --preemptible
    > If provided, instances will be preemptible and time-limited. Instances may be preempted to free up resources for standard VM instances, and will only be able to run for a limited amount of time. Preemptible instances can not be restarted and will not migrate.
* Example
    - CREATE INSTANCE WITH 4 vCPUs and 5 GB MEMORY
        ```bash
        gcloud compute instances create my-vm --custom-cpu 4 --custom-memory 5
        ```

    - ENABLE PREEMPTIBLE OPTION
        ```bash
        gcloud compute instances create my-vm --zone us-central1-b --preemptible
        ```

---
## 2.3.- Planning and configuring data storage options
* Video
    - [From blobs to relational tables: Where do I store my Data?](https://www.youtube.com/watch?v=rn_68hBqt20)
    - [Platform Overview - Data & Storage](https://www.youtube.com/watch?v=tc2940Zwvyk)
* Imagenes
    - ![Test Image 2](imagen2.PNG)

    - ![Test Image 1](imagen1.png)

### 2.3.1.- Product choice

#### 2.3.1.1.- Cloud SQL

    Cloud SQL is a fully-managed database service that makes it easy to set up, maintain, manage, and administer your relational databases on Google Cloud Platform.

* Doc Refence
    - [SQL](https://cloud.google.com/sql/docs/)
    - [What is Cloud SQL](https://www.youtube.com/watch?v=Kl8ig2BtLAY)

#### 2.3.1.2.- BigQuery

    A fast, highly scalable, cost-effective and fully-managed enterprise data warehouse for analytics at any scale

    BigQuery is Google's serverless, highly scalable, low cost enterprise data warehouse designed to make all your data analysts productive. Because there is no infrastructure to manage, you can focus on analyzing data to find meaningful insights using familiar SQL and you don't need a database administrator. BigQuery enables you to analyze all your data by creating a logical data warehouse over managed, columnar storage as well as data from object storage, and spreadsheets. BigQuery makes it easy to securelyshare insights within your organization and beyond as datasets, queries, spreadsheets and reports. BigQuery allows organizations tocapture and analyze data in real-time using its powerful streaming ingestion capability so that your insights are always current. BigQuery is free for up to 1TB of data analyzed each month and 10GB of data stored.

* Doc Reference
    - [BigQuery](https://cloud.google.com/bigquery/)
    - [What is BigQuery](https://www.youtube.com/watch?v=d3MDxC_iuaw)

#### 2.3.1.3.- Cloud Spanner

    The first horizontally scalable, strongly consistent, relational database service


* Doc Refence
    - [Spanner](https://cloud.google.com/spanner/)
    - [PDF](https://www.snia.org/sites/default/files/SDCIndia/2017/Slides/Rohit%20Gupta%20-%20Google%20-%20Cloud%20Spanner.pdf)
    - [What is Cloud Spanner](https://www.youtube.com/watch?v=bUSU1e9j8wc)

* Table
- ![Test Image 3](imagen3.PNG)

#### 2.3.1.4.- Cloud Bigtable
    A fully managed, scalable NoSQL database service for large analytical and operational workloads
* Doc References
    - [BigTable](https://cloud.google.com/bigtable/)
---
### 2.3.2.- Choosing storage options

    Cloud Storage is a service for storing your objects in Google Cloud. An object is an immutable piece of data consisting of a file of any format. You store objects in containers called buckets. All buckets are associated with a project, and you can group your projects under an organization.

#### 2.3.2.1 - Regional
    Storing frequently accessed in the same region as your Google Cloud DataProc or Google Compute Engine instances that use it, such as for data analytics.
#### 2.3.2.2 - Multi-regional
    Storing data that is frequently accessed ("hot" objects) around the world, such as serving website content, streaming videos, or gaming and mobile applications.
#### 2.3.2.3 - Nearline
    Data you do not expect to access frequently (i.e., no more than once per month). Ideal for back-up and serving long-tail multimedia content.
#### 2.3.2.4 - Coldline
    Data you expect to access infrequently (i.e., no more than once per year). Typically this is for disaster recovery, or data that is archived and may or may not be needed at some future time.

* Table
- ![Test Image 3](imagen4.PNG)

---
## 2.4.- Planning and configuring network resources

### 2.4.1.- Differentiating load balancing options
    By using Cloud Load Balancing, you can serve content as close as possible to your users on a system that can respond to over one million queries per second.

    Cloud Load Balancing is a fully distributed, software-defined managed service. It isn't hardware-based, so you don't need to manage a physical load balancing infrastructure.

    Google Cloud offers the following load balancing features:

        - Single IP address to serve as the frontend
        - Automatic intelligent autoscaling of your backends
        - External load balancing for when your users reach your applications from the internet
        - Internal load balancing for when your clients are inside of Google Cloud
        - Regional load balancing for when your applications are available in a single region
        - Global load balancing for when your applications are available across the world
        - Pass-through load balancing (see also direct server return (DSR) or direct routing)
        - Proxy-based load balancing (as an alternative to pass-through)
        - Layer 4-based load balancing to direct traffic based on data from network and transport layer protocols, such as IP address and TCP or UDP port
        - Layer 7-based load balancing to add content-based routing decisions based on attributes, such as the HTTP header and the uniform resource identifier
        - Integration with Cloud CDN for cached content delivery

- ![Chosse lb](imagen5.png)

* Doc References
    - [Type Cloud Load Balancer](https://cloud.google.com/load-balancing/docs/load-balancing-overview#types-of-cloud-load-balancing)
    - [Chossing Load Balancer](https://cloud.google.com/load-balancing/docs/choosing-load-balancer)
    - [Load balancer features](https://cloud.google.com/load-balancing/docs/features)
* Table
- ![Chosse lb](https://cloud.google.com/load-balancing/images/choose-lb.svg)
---
### 2.4.2.- Identifying resource locations in a network for availability

    - logical location in the network (i.e. subnets, load balancers, and what not).
    - physical location in the world.

    The logical location can also be helpful for things like setting security boundaries, but I think the physical location also matters a lot to availability. In particular, you would want to spread your resources across at least multiple (availability) zones and as you've suggested load balance across them to get rid of the single points of failure.

    Basically, I would choose to read this line as "Identifying (physical) resource locations for availability and also (logically) networking them for availability."

---
### 2.4.3.- Configuring Cloud DNS

*Enable the DNS API*
```bash
gcloud services enabled dns.googleapis.com
```

*Create a managed public zone*
```bash
gcloud dns managed-zones create my_zone --dns-name=cesarcastillo.cl  --description="my zone for cesarcastillo.cl" --dnssec-state=off
```

*The Zone details page*
```bash
gcloud dns managed-zones list
```

*Create a record to point the domain to an external IP address*


* Doc References
    - [Setting up a domain using Cloud DNS](https://cloud.google.com/dns/docs/tutorials/create-domain-tutorial)
    - [Cloud DNS](https://cloud.google.com/dns/docs/overview)
    - [Commands gcloud](https://cloud.google.com/sdk/gcloud/reference/dns?hl=es)
* Video
    - [How to Configure DNS in Google Cloud](https://www.youtube.com/watch?v=1SxiBYqxwAM)
    - [Administra tus dominios con el servicio de Google Cloud DNS](https://www.youtube.com/watch?v=sw-NhOwOQdI)
---