# 3.-  Deploying and implementing a cloud solution

## 3.5.- Deploying and implementing networking resources
---
### 3.5.2.- Launching a Compute Engine instance with custom network configuration

Locating IP addresses for an instance
```bash
gcloud compute instances list
```
NAME|ZONE|MACHINE_TYPE|PREEMPTIBLE|INTERNAL_IP|EXTERNAL_IP|STATUS
---|---|---|---|---|---|---
hulk|us-central1-c|m1-ultramem-160|true||192.0.2.1|  |RUNNING
my-instance|us-central1-c|us-standard-2||192.51.100.1|203.224.0.113|RUNNING

```bash
gcloud compute instances describe my-instance \
  --format='get(networkInterfaces[0].networkIP)'
    192.0.2.1

gcloud compute instances describe instance-name \
  --format='get(networkInterfaces[0].accessConfigs[0].natIP)'
    203.224.0.113
```
---
#### **Internal-only IP address**
If a virtual machine (VM) instance requires a fixed internal IP address that does not change, you can obtain a static internal IP address for that VM using one of the following options:

* Reserve a new static internal IP address and then assign the address when creating the VM.
* Promote an existing ephemeral internal IP address to become a static internal IP address

___How to reserve a static internal IP address___
> You can reserve a static internal IP address before creating the associated resource, or you can create the resource with an ephemeral internal IP address and then promote that ephemeral IP address to a static internal IP address
- **Create a subnet** from your VPC network.
- **Reserve an internal IP address from the subnet's primary IP range**. This step creates an internal IP address resource containing that specific internal IP address. This step also prevents Google Cloud from automatically allocating that address as an ephemeral address.
- Use the reserved **internal IP address by associating** it with a **VM instance** or **an internal load balancer** when you create the VM or load balancer resource.

```bash
> to reserve an automatically allocated internal IP address from a subnet:
    gcloud compute addresses create example-address-1 \
    --region us-central1 --subnet subnet-1

> To reserve a specific internal IP address from a subnet:
    gcloud compute addresses create example-address-1 \
    --region us-central1 --subnet subnet-1 --addresses 10.128.0.12
````
___Creating a VM instance with a specific internal IP address___
```bash
> You can choose a specific internal IP address to assign to an instance when you create the instance

gcloud compute instances create INSTANCE_NAME
     --private-network-ip IP_ADDRESS
```
___Using a static internal IP address for a secondary network interface___
```bash
> When you create a VM instance with multiple network interfaces, you can use a reserved static internal IP address for both primary and secondary network interfaces
    gcloud compute addresses create my-second-ip-address \
    --region us-central1 --subnet subnet-b

    gcloud compute instances create my-instance \
    --image-family IMAGE_FAMILY \
    --image-project IMAGE_PROJECT \
    --network-interface subnet=subnet-a,no-address \
    --network-interface \
      subnet=subnet-b,private-network-ip=my-second-ip-address,no-address
```
___Deleting a static internal IP address___
```bash
gcloud compute addresses delete example-address-to-delete \
    --region us-west1
```
---
#### **Google private access**
- Doc Ref : [Configuring Private Google Access](https://cloud.google.com/vpc/docs/configure-private-google-access)

By default, when a Compute Engine VM lacks an external IP address assigned to its network interface, it can only send packets to other internal IP address destinations. You can allow these VMs to connect to the set of external IP addresses used by Google APIs and services by enabling Private Google Access on the subnet used by the VM's network interface.

> Enabling Private Google Access
```bash
gcloud compute networks subnets list --filter=NETWORK_NAME

gcloud compute networks subnets update SUBNET_NAME \
--region=REGION \
--enable-private-ip-google-access

gcloud compute networks subnets describe SUBNET_NAME \
--region=REGION \
--format="get(privateIpGoogleAccess)"

> When creating a new subnet, use the --enable-private-ip-google-access flag to enable Private Google Access
    gcloud compute networks subnets create SUBNET_NAME \
    --region=REGION \
    --network=NETWORK_NAME \
    --range=PRIMARY_IP_RANGE \
    --enable-private-ip-google-access
```
> Disabling Private Google Access
```bash
gcloud compute networks subnets update SUBNET_NAME \
    --region=REGION \
    --no-enable-private-ip-google-access
```
---
### **Static external and private IP address**
-Doc References : [Reserving a static external IP address](https://cloud.google.com/compute/docs/ip-addresses/reserve-static-external-ip-address)

If a virtual machine (VM) instance requires a fixed external IP address that does not change, you can obtain a static external IP address for that instance by using one of the following options:

Reserve a new static external IP address and then assign the address to a new VM instance.
Promote an existing ephemeral external IP address to become a static external IP address.

You can reserve two types of external IP addresses:
- A regional IP address which can be used by VM instances with one or more network interfaces or by Network load balancers.
- A global IP address which can be used for global load balancers: HTTP(S), SSL proxy, and TCP proxy.

__Reserving a new static external IP address__
```bash
gcloud compute addresses create ADDRESS_NAME \
    --global \
    --ip-version [IPV4 | IPV6]

gcloud compute addresses create ADDRESS_NAME \
    --region REGION

gcloud compute addresses describe ADDRESS_NAME
```
___Assigning a static external IP address to a new VM instance__
```bash
gcloud compute instances create INSTANCE_NAME --address IP_ADDRESS
```
__Changing or assigning an external IP address to an existing instance__
```bash
gcloud compute instances describe INSTANCE_NAME

gcloud compute instances delete-access-config INSTANCE_NAME \
    --access-config-name "ACCESS_CONFIG_NAME"

gcloud compute instances add-access-config INSTANCE_NAME \
   --access-config-name "ACCESS_CONFIG_NAME" --address IP_ADDRESS
```

If you want Compute Engine to __assign an ephemeral external IP address__ rather than using a static external IP address, omit the --address IP_ADDRESS property:
```bash
    gcloud compute instances add-access-config INSTANCE_NAME \
    --access-config-name "ACCESS_CONFIG_NAME"
```
---
### **network tags**
- Doc Ref : [Configuring network tags](https://cloud.google.com/vpc/docs/add-remove-network-tags)

*Network Tags: Assign network tags to apply firewall rules to specific VM instances.*

__Adding and removing tags__
- Adding tags when creating a VM
```bash
    gcloud compute instances create [INSTANCE-NAME] \
    --zone [ZONE] \
    --tags [TAGS] \
    ...other parameters as needed.
```
- Adding tags to an existing VM
```bash
    gcloud compute instances add-tags [INSTANCE-NAME] \
    --zone [ZONE] \
    --tags [TAGS]
```
- Removing tags
```bash
    gcloud compute instances remove-tags [INSTANCE-NAME] \
    --zone [ZONE] \
    --tags [TAGS]
```
