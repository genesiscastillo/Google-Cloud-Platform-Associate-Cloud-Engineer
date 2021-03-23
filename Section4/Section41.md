# 4.- Ensuring successful operation of a cloud solution
## 4.1.- Managing Compute Engine resources
### 4.1.1.- Managing a single VM instance

**start**
```bash
    gcloud compute instances start example-instance  --zone=us-central1-a
```
**stop**
```bash
    gcloud compute instances stop test-instance
```
**edit configuration**
```bash
    gcloud compute instances update-access-config example-instance \
    --network-interface=nic0 \
    --zone=us-central1-b
```
**delete an instance**
```bash
gcloud compute instances delete instance-1 --zone=us-central2-a
```
**copy files to and from Google Compute Engine virtual machines**
*To copy a remote directory, ~/narnia, from example-instance to the ~/wardrobe directory of your local host, run:*
```bash
gcloud compute scp --recurse example-instance:~/narnia ~/wardrobe
```
*Conversely, files from your local computer can be copied to a virtual machine:*
```bash
gcloud compute scp ~/localtest.txt ~/localtest2.txt  example-instance:~/narnia
```

---
### 4.1.2.- SSH/RDP to the instance
```bash
gcloud compute firewall-rules create --network=NETWORK  default-allow-ssh --allow=tcp:22

gcloud compute ssh example-instance --zone=us-central1-a
```
---
### 4.1.3.- Attaching a GPU to a new instance and installing CUDA libraries
- Doc [Install CUDA](https://towardsdatascience.com/installing-cuda-on-google-cloud-platform-in-10-minutes-9525d874c8c1)

**Attaching a GPU to a new instance**
You can attach GPUs only to instances with a *predefined machine type* or *custom machine type* that you are able to create in a zone. __GPUs are not supported on shared-core machine types or memory-optimized machine types.__

[Creating VM with attached GPUs](https://cloud.google.com/compute/docs/gpus/create-vm-with-gpus)

*Creating VMs with attached GPUs (A100 GPUs)*
- To create and start a VM use the gcloud compute instances create command with the following flags. VMs with GPUs cannot live migrate, make sure that you set the --maintenance-policy TERMINATE flag.
```bash
    gcloud compute instances create VM_NAME \
    --machine-type MACHINE_TYPE \
    --zone ZONE \
    [--image IMAGE | --image-family IMAGE_FAMILY] \
    --image-project IMAGE_PROJECT \
    --maintenance-policy TERMINATE --restart-on-failure \
    [--preemptible]
```
In these examples, VMs are created with attached NVIDIA® A100 GPUs 
Create a VM using the tf2-ent-2-3-cu110 image and the a2-highgpu-1g machine type. In this example, optional flags such as boot disk size and scope are specified.
```bash
gcloud compute instances create VM_NAME \
   --project PROJECT_ID \
   --zone us-central1-c \
   --machine-type a2-highgpu-1g \
   --maintenance-policy TERMINATE --restart-on-failure \
   --image-family tf2-ent-2-3-cu110 \
   --image-project deeplearning-platform-release \
   --boot-disk-size 200GB \
   --metadata "install-nvidia-driver=True,proxy-mode=project_editors" \
   --scopes https://www.googleapis.com/auth/cloud-platform
```
*Creating VMs with attached GPUs (other GPU types)*
For example, you can use the following gcloud command to start an Ubuntu 16.04 VM with 1 NVIDIA K80 GPU and 2 vCPUs in the us-east1-d zone
```bash
gcloud compute instances create gpu-instance-1 \
    --machine-type n1-standard-2 \
    --zone us-east1-d \
    --accelerator type=nvidia-tesla-k80,count=1 \
    --image-family ubuntu-1604-lts \
    --image-project ubuntu-os-cloud \
    --maintenance-policy TERMINATE --restart-on-failure
```
**Install CUDA 10.0 cuDNN 7.6.5 Ubuntu 16.04**
*install.sh*
```bash
#Get PPA repo drivers and Install CUDA 10.0
curl -O http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1604/x86_64/cuda-repo-ubuntu1604_10.0.130-1_amd64.deb
sudo dpkg -i cuda-repo-ubuntu1604_10.0.130-1_amd64.deb
sudo apt-key adv --fetch-keys http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1604/x86_64/7fa2af80.pub
sudo apt-get update
sudo apt-get install cuda-10-0 cuda-drivers -y

#Install cuda-compatibility 10.0
sudo nvidia-smi -pm 1
sudo apt-get install cuda-compat-10.0
sudo apt-get update

#Set the environment for cuda 10.0
nano ~/.bashrc
export PATH=/usr/local/cuda-10.0/bin${PATH:+:${PATH}}$ 
export LD_LIBRARY_PATH=/usr/local/cuda-10.0/lib64${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}
source ~/.bashrc

#Fetch cuDNN 
CUDNN_TAR_FILE="cudnn-10.0-linux-x64-v7.6.5.32.tgz"
wget https://developer.nvidia.com/compute/machine-learning/cudnn/secure/7.6.5.32/Production/10.0_20191031/cudnn-10.0-linux-x64-v7.6.5.32.tgz
sudo tar -xzvf ${CUDNN_TAR_FILE}

#copy the files in cuda toolkit directory 
sudo cp cuda/include/cudnn.h /usr/local/cuda/include
sudo cp cuda/lib64/libcudnn* /usr/local/cuda/lib64
sudo chmod a+r /usr/local/cuda/include/cudnn.h /usr/local/cuda/lib64/libcudnn*

## To verify the installation
nvcc -V  # this should print the CUDA version installed on the system
```
---
### 4.1.4.- Viewing current running VM Inventory
Use OS inventory management to collect and view operating system details for your VM instances (VMs). These operating system details include information such as hostname, operating system, and kernel version as well as installed packages, and available package updates for the operating system. For a list of common scenarios for using OS inventory management, review When to use OS inventory management.

```bash
gcloud compute instances os-inventory describe VM-NAME

gcloud compute instances os-inventory list-instances
```
NAME | ZONE | MACHINE_TYPE | PREEMPTIBLE | INTERNAL_IP | EXTERNAL_IP | STATUS |
---|---|---|---|---|---|---
inventory-instance|   us-east1-b|    e2-standard-2| |192.0.2.1 | | RUNNING
instance-inventory1|  us-west1-b|    e2-standard-2| |192.0.2.2 | | RUNNING
instance-inventory2|  asia-east2-b|  e2-standard-2| |192.0.2.3 | | RUNNING

```bash
gcloud compute instances os-inventory list-instances --inventory-filter="Hostname~instance-*"
```
NAME | ZONE | MACHINE_TYPE | PREEMPTIBLE | INTERNAL_IP | EXTERNAL_IP | STATUS 
---|---|---|---|---|---|---
instance-inventory1|  us-west1-b |   e2-standard-2| | 192.0.2.2 | | RUNNING
instance-inventory2|  asia-east2-b | e2-standard-2| | 192.0.2.3 | | RUNNING
---
### 4.1.5.- Working with snapshots
**create a snapshot from a VM**

To create a snapshot named snapshot-test of a persistent disk named test in zone us-central1-a, run:
```bash
gcloud compute disks snapshot test --zone=us-central1-a  --snapshot-names=snapshot-test  --description="This is an example snapshot"
```
**Creating a new persistent disk from a snapshot**
```bash
gcloud compute disks create DISK_NAME \
    --size=DISK_SIZE \
    --source-snapshot=SNAPSHOT_NAME \
    --type=DISK_TYPE
```
--source-snapshot=SOURCE_SNAPSHOT
A source snapshot used to create the disks. It is safe to delete a snapshot after a disk has been created from the snapshot. In such cases, the disks will no longer reference the deleted snapshot. To get a list of snapshots in your current project, run gcloud compute snapshots list. A snapshot from an existing disk can be created using the gcloud compute disks snapshot command. This flag is mutually exclusive with --image.
When using this option, the size of the disks must be at least as large as the snapshot size. Use --size to adjust the size of the disks.
```bash
gcloud compute instances attach-disk INSTANCE_NAME \
    --disk DISK_NAME
```
**view snapshots**
```bash
gcloud compute snapshots describe SNAPSHOT_NAME

gcloud compute snapshots list
```
 **delete a snapshot**
```bash
    gcloud compute snapshots delete SNAPSHOT_NAME
```
---
### 4.1.6.- Working with Images
**create an image from a VM or a snapshot**
- Create an image from a source disk
```bash
gcloud compute images create IMAGE_NAME \
  --source-disk=SOURCE_DISK \
  --source-disk-zone=ZONE \
  [--family=IMAGE_FAMILY] \
  [--storage-location=LOCATION] \
  [--force]
```
- Create an image from a source image
```bash
gcloud compute images create IMAGE_NAME \
  --source-image=SOURCE_IMAGE \
  [--source-image-project=IMAGE_PROJECT] \
  [--family=IMAGE_FAMILY] \
  [--storage-location=LOCATION]
```
- Create an image from a snapshot:
```bash
gcloud compute images create IMAGE_NAME \
  --source-snapshot SOURCE_SNAPSHOT \
  [--storage-location LOCATION]
```
**view images**
```bash
gcloud compute images describe IMAGE_NAME
```
**delete an image**
```bash
    gcloud compute images delete IMAGE_NAME
```
---
### 4.1.7.- Working with Instance Groups

**set auto scaling parameters**
You can configure managed instance groups to automatically add or remove VMs based on their workloads. Your applications can gracefully handle increases in traffic, and you can reduce your costs when the need for compute resources is lower

**assign instance template**
To create a group of preemptible instances, set the premptible option in an instance template, and then use the template to create the managed instance group.
```bash
gcloud compute instance-templates create INSTANCE_TEMPLATE \
    --preemptible
```
**create an instance template**
The names that you assign to these managed instances persist if the MIG recreates the VM
```bash
gcloud compute instance-templates create INSTANCE_TEMPLATE \
    --preemptible
```
**remove instance group**
When you delete a managed instance group, all VMs in the group are deleted. If you must keep any of the VMs in this managed instance group, abandon the instances first to remove the VMs from the group. Then, delete the managed instance group.
```bash
gcloud compute instance-groups managed delete INSTANCE_GROUP_NAME \
    --zone ZONE
```
### 4.1.8.- Working with management interfaces
Every instance in a VPC network has a default network interface. You can create additional network interfaces attached to your VMs, but each interface must attach to a different VPC network. Multiple network interfaces enable you to create configurations in which an instance connects directly to several VPC networks. Each of the interfaces must have an internal IP address, and each interface can also have an external IP address. Each instance can have up to 8 interfaces, depending on the instance's type

**Cloud Console**
- [Pfsense with multiple interfaces in GCP](https://www.youtube.com/watch?v=cMCqZ4nd6ls)
- 
**Cloud Shell**
```bash
gcloud compute instances create VM-appliance \
    --network-interface subnet=subnet-perimeter,address='reserved-address' \
    --network-interface subnet=subnet-1,no-address \
    --network-interface subnet=subnet-2,no-address \
    --network-interface subnet=subnet-3,no-address \
    --network-interface subnet=subnet-4,no-address \
    --machine-type=n1-standard-4
```
**GCloud SDK**
```bash
gcloud compute instances create vm-appliance \
    --network-interface subnet=subnet0,no-address \
    --network-interface subnet=subnet1 \
    --network-interface subnet=subnet2,no-address \
    --machine-type n1-standard-4
```
