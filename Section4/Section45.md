# 4.- Ensuring successful operation of a cloud solution
## 4.1.- Managing Compute Engine resources
---
## 4.5.- Managing networking resources
---
### 4.5.1.- Adding a subnet to an existing VPC

gcloud compute networks create NETWORK \
    --subnet-mode=auto \
    --bgp-routing-mode=DYNAMIC_ROUTING_MODE \
    --mtu=MTU

gcloud compute networks subnets create SUBNET \
    --network=NETWORK \
    --range=PRIMARY_RANGE \
    --region=REGION

gcloud compute networks subnets list

gcloud compute networks subnets list \
   --network=NETWORK

gcloud compute networks subnets list \
   --filter="region:( REGION … )"

gcloud compute networks subnets delete SUBNET \
    --region=REGION


---
### 4.5.2.- Expanding a CIDR block subnet to have more IP addresses

Region|	IP range (CIDR)|	Default gateway|	Usable addresses (inclusive)
---|---|---|---
asia-east1|	10.140.0.0/20|	10.140.0.1|	10.140.0.2 to 10.140.15.253
us-central1|	10.128.0.0/20|	10.128.0.1|	10.128.0.2 to 10.128.15.253
```bash
gcloud compute networks subnets expand-ip-range SUBNET \
  --region=REGION \
  --prefix-length=PREFIX_LENGTH
```
**PREFIX_LENGTH** is a subnet mask size in bits. If the primary IP range is 10.1.2.0/24, you can supply 20 to reduce the subnet mask to 20 bits, which changes the primary IP range to 10.1.2.0/20
---
### 4.5.3.- Reserving static external or internal IP addresses

```bash
gcloud compute addresses create ADDRESS_NAME \
    --global \
    --ip-version [IPV4 | IPV6]

gcloud compute addresses create ADDRESS_NAME \
    --region REGION

gcloud compute instances create INSTANCE_NAME --address IP_ADDRESS

gcloud compute addresses list

gcloud compute addresses describe ADDRESS_NAME

gcloud compute addresses delete ADDRESS_NAME
```
----
### 4.5.4.- Working with management interfaces
- Cloud Console
-Cloud Shell
- Cloud SDK
