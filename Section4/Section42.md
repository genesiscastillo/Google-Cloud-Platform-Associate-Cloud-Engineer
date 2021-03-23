# 4.- Ensuring successful operation of a cloud solution
## 4.1.- Managing Compute Engine resources

## 4.2.- Managing Kubernetes Engine resources
### 4.2.1.- Viewing current running cluster inventory
**nodes**
kubectl get nodes
**pods**
kubectl get pods
**services**
kubectl get services

### 4.2.2.- Browsing the container image repository and viewing container image details


### 4.2.3.- Working with nodes
Resize an existing cluster to a provided size.
If you have multiple node pools, you must specify which node pool to resize by using the --node-pool flag. You are not required to use the flag if you have a single node pool.

When increasing the size of a container cluster, the new instances are created with the same configuration as the existing instances. Existing pods are not moved onto the new instances, but new pods (such as those created by resizing a replication controller) will be scheduled onto the new instances.

When decreasing a cluster, the nodes are drained. As a result, the pods running on these nodes are gracefully terminated. If your pods are being managed by a workload controller, the controller will attempt to reschedule them onto the remaining instances. If your pods are not managed by a workload controller, they will not be restarted. Note that when resizing down, instances running pods and instances without pods are not differentiated. Resize will pick instances to remove at random.
**add a node** 
```bash
gcloud container clusters resize sample-cluster --num-nodes=2
```
**edit a node**
```bash
gcloud container clusters resize sample-cluster --num-nodes=2
```
**remove a node**
```bash
gcloud container clusters resize sample-cluster --num-nodes=2
```

### 4.2.4.- Working with pods
**add pods**
*hello-app-deploy.yaml*
```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: my-app
spec:
  replicas: 3
  selector:
    matchLabels:
      run: my-app
  template:
    metadata:
      labels:
        run: my-app
    spec:
      containers:
      - name: hello-app
        image: gcr.io/google-samples/hello-app:1.0
```
```bash
    kubectl apply -f hello-app-deploy.yaml
```
**Inspecting the Deployment**
```bash
kubectl describe deployment my-app
kubectl get pods -l [KEY]=[VALUE]
kubectl describe pod pod-my-app-87sh767-98s77sk
kubectl get deployments my-app -o yaml
```
**edit pods**
```bash
    kubectl set image deployment nginx nginx=nginx:1.9.1
    kubectl apply -f hello-app-deploy.yaml
```
**Scaling a Deployment**
```bash
kubectl scale deployment my-app --replicas 5
```
**remove pods**
```bash
kubectl delete deployment my-app

kubectl delete -f hello-app-deploy.yaml

kubectl delete pod pod-my-app-87sh767-98s77sk --now

kubectl delete pod pod-my-app-87sh767-98s77sk --force

kubectl delete pods --all
```
### 4.2.5.- Working with services
[Connecting Applications with Services](https://kubernetes.io/docs/concepts/services-networking/connect-applications-service/)

**add a service**
```bash
    kubectl expose deployment/my-nginx
```
**edit a service**
```bash
    kubectl edit svc my-nginx

    kubectl get svc my-nginx

    kubectl describe svc my-nginx
```
**remove a service**
```bash
    kubectl delete svc my-nginx
```
### 4.2.6.- Working with management interfaces
- Cloud Console
- Cloud Shell
- Cloud SDK
