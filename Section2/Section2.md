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
---
## 2.4.- Planning and configuring network resources

---