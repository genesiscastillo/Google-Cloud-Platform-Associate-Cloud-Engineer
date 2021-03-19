# 3.-  Deploying and implementing a cloud solution

## 3.2 Deploying and implementing Kubernetes Engine resources

* [Kubernetes Design and Architecture](https://github.com/kubernetes/community/blob/master/contributors/design-proposals/architecture/architecture.md)

---
### 3.2.1.- Deploying a Kubernetes Engine cluster

```bash
gcloud components install kubectl

gcloud config set project project-id

gcloud config set compute/zone compute-zone

gcloud container clusters create cluster-name --num-nodes=1

gcloud container clusters get-credentials cluster-name
```
---
### 3.2.2.- Deploying a container application to Kubernetes Engine using pods

```bash
kubectl create deployment hello-server --image=gcr.io/google-samples/hello-app:1.0

kubectl expose deployment hello-server --type LoadBalancer \
  --port 80 --target-port 8080

kubectl get pods

kubectl get service hello-server

http://external-ip/
    
kubectl delete service hello-server

gcloud container clusters delete cluster-name

```
---
### 3.2.3.- Configuring Kubernetes Engine application monitoring and logging
- Video
    * [Stack Driver Monitoring, Logging and Alerting on Google Cloud Kubernetes Engine](https://www.youtube.com/watch?v=oNEl-H0QWWg)

- Doc References
    * [Logging StackDriver](https://kubernetes.io/docs/tasks/debug-application-cluster/logging-stackdriver/)
    * [Monitoring Kubernetes Clusters on GKE](https://medium.com/google-cloud/gke-monitoring-84170ea44833)

