# 4.- Ensuring successful operation of a cloud solution
## 4.2.- Managing Kubernetes Engine resources
---
### 4.2.1.- Viewing current running cluster inventory
**nodes**
kubectl get nodes
**pods**
kubectl get pods
**services**
kubectl get services

### 4.2.2.- Browsing the container image repository and viewing container image details

> PENDIENTE AGREAGR IMAGEN

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

**Terminology related to IP addresses in Kubernetes**
- *ClusterIP*: The IP address assigned to a Service. In other documents, it may be called the "Cluster IP". This address is stable for the lifetime of the Service, as discussed in the Services section in this topic.
- *Pod IP*: The IP address assigned to a given Pod. This is ephemeral, as discussed in the Pods section in this topic.
- *Node IP*: The IP address assigned to a given node.

**Networking inside the cluster**


- *IP allocation*
    - **Each node has an IP address assigned from the cluster's Virtual Private Cloud (VPC) network**. This node IP provides connectivity from control components like kube-proxy and the kubelet to the Kubernetes API server. This IP is the node's connection to the rest of the cluster.
    - **Each node has a pool of IP addresses that GKE assigns Pods running on that node (a /24 CIDR block by default)**. You can optionally specify the range of IPs when you create the cluster. The Flexible Pod CIDR range feature allows you to reduce the size of the range for Pod IPs for nodes in a given node pool.

    > Note: For Standard clusters, you can run a maximum of 110 Pods on a node with a /24 range, not 256 as you might expect. This provides a buffer so that Pods don't become unschedulable due to a transient lack of IP addresses in the Pod IP range for a given node. For ranges smaller than /24, roughly half as many Pods can be scheduled as IP addresses in the range. Autopilot clusters can run a maximum of 32 Pods per node.

    - **Each Pod has a single IP address assigned from the Pod CIDR range of its node**. This IP address is shared by all containers running within the Pod, and connects them to other Pods running in the cluster.

    - **Each Service has an IP address, called the ClusterIP**, assigned from the cluster's VPC network. You can optionally customize the VPC network when you create the cluster.


- *Pods*

    In Kubernetes, **a Pod is the most basic deployable unit within a Kubernetes cluster**. A Pod runs one or more containers. Zero or more Pods run on a node. Each node in the cluster is part of a node pool. In GKE, these nodes are virtual machines, each running as an instance in Compute Engine.

    ![pod](https://cloud.google.com/kubernetes-engine/images/networking-overview_single-node.png)

- *Services*

    In Kubernetes, **you can assign arbitrary key-value pairs called labels to any Kubernetes resource**. Kubernetes uses labels to group multiple related Pods into a logical unit called a Service. **A Service has a stable IP address and ports, and provides load balancing** among the set of Pods whose labels match all the labels you define in the label selector when you create the Service.

    ![services](https://cloud.google.com/kubernetes-engine/images/networking-overview_two-services.png)

**Networking outside the cluster**

GKE provides three different types of load balancers to control access and to spread incoming traffic across your cluster as evenly as possible. You can configure one Service to use multiple types of load balancers simultaneously.

- **External load balancers** manage traffic coming from outside the cluster and outside your Google Cloud Virtual Private Cloud (VPC) network. They use forwarding rules associated with the Google Cloud network to route traffic to a Kubernetes node.
- **Internal load balancers** manage traffic coming from within the same VPC network. Like external load balancers, they use forwarding rules associated with the Google Cloud network to route traffic to a Kubernetes node.
- **HTTP(S) load balancers** are specialized external load balancers used for HTTP(S) traffic. They use an Ingress resource rather than a forwarding rule to route traffic to a Kubernetes node.

![nrouting](https://cloud.google.com/kubernetes-engine/images/networking-overview_routing.png)



- Cloud Console
- Cloud Shell
- Cloud SDK
