# 3.-  Deploying and implementing a cloud solution

## 3.1.- Deploying and implementing Compute Engine resources
---
### 3.1.1.- Launching a compute instance using Cloud Console and Cloud SDK (gcloud)

#### **assign disks**

* Doc Reference
    - [--disk](https://cloud.google.com/sdk/gcloud/reference/compute/instances/create?hl=es#--disk)

```bash
--disk=[auto-delete=AUTO-DELETE],[boot=BOOT],[device-name=DEVICE-NAME],[mode=MODE],[name=NAME],[scope=SCOPE]
```
    Attaches persistent disks to the instances. The disks specified must already exist.
* name
    - The disk to attach to the instances. When creating more than one instance and using this property, the only valid mode for attaching the disk is read-only (see mode below).
* mode
    - Specifies the mode of the disk. Supported options are ro for read-only and rw for read-write. If omitted, rw is used as a default. It is an error for mode to be rw when creating more than one instance because read-write disks can only be attached to a single instance.
* boot
    - If yes, indicates that this is a boot disk. The virtual machines will use the first partition of the disk for their root file systems. The default value for this is no.
* device-name
    - An optional name that indicates the disk name the guest operating system will see. If omitted, a device name of the form persistent-disk-N will be used.
* auto-delete
    - If yes, this persistent disk will be automatically deleted when the instance is deleted. However, if the disk is later detached from the instance, this option won't apply. The default value for this is yes.
* scope
    - Can be zonal or regional. If zonal, the disk is interpreted as a zonal disk in the same zone as the instance (default). If regional, the disk is interpreted as a regional disk in the same region as the instance. The default value for this is zonal.

#### **availability policy**
    Compute Engine realiza un mantenimiento regular de su infraestructura. En esta página, se describen los tipos de eventos de mantenimiento y sus frecuencias aproximadas, y el modo en que puedes configurar las opciones de disponibilidad de instancias a fin de establecer el comportamiento de las instancias de VM cuando ocurren estos eventos

* Choosing availability policies
    - The VM instance's **maintenance behavior**, que determina si la instancia se migra en vivo o se detiene cuando ocurre un evento de mantenimiento.
    - The instance's **restart behavior**, que determina si la instancia se reinicia de forma automática si falla o se detiene.

        - ***Live Migrate***.- ocurre cuando Compute Engine migra automáticamente tu instancia lejos de un evento de mantenimiento de infraestructura, y la instancia permanece en ejecución durante la migración.
            - compute.instances.migrateOnHostMaintenance
        - ***Stop and (optionally) restart***.- Si no deseas que tu instancia realice una migración en vivo, puedes optar por detenerla y, de manera opcional, reiniciarla.
            - compute.instances.terminateOnHostMaintenance
        - ***Automatic restart***.- Si la instancia se configuró para detenerse cuando hay un evento de mantenimiento, o si esta falla debido a un problema subyacente en el hardware, puedes configurar Compute Engine para que la reinicie de forma automática mediante la configuración del campo automaticRestart en true
            - compute.instances.automaticRestart

    ```bash
    gcloud compute operations list --filter="zone:(us-central1-c)"
    ```
    
* Setting availability policies

    *donde: MAINTENANCE_POLICY -> TERMINATE or MIGRATE*

    - Setting options during instance creation
    ```bash
    gcloud compute instances create INSTANCE_NAME \
    --maintenance-policy MAINTENANCE_POLICY \
    [--no-restart-on-failure]
    ```
    - Updating options for an instance
    ```bash
    gcloud compute instances set-scheduling INSTANCE_NAME \
    --maintenance-policy MAINTENANCE_POLICY \
    [--no-restart-on-failure | --restart-on-failure]
    ```
    - Testing your availability policies
    ```bash
    gcloud compute instances simulate-maintenance-event \
    INSTANCE_NAME --zone ZONE
    ```

- Doc References
    * [Setting instance availability policies](https://cloud.google.com/compute/docs/instances/setting-instance-scheduling-options)

#### **SSH keys**
- Doc References
    * [SSH with security keys](https://cloud.google.com/compute/docs/tutorials/ssh-with-sk)
    * [Connecting apps to instances using SSH](https://cloud.google.com/compute/docs/tutorials/service-account-ssh)
---
### 3.1.2.- Creating an autoscaled managed instance group using an instance 

- Doc Reference
    * [Autoscaling with Managed Instance Groups](https://rajeevkghosh.medium.com/google-cloud-autoscaling-with-managed-instance-groups-a01e35ca95ea)
- Video
    * [Create Managed Instance Group
](https://www.youtube.com/watch?v=AXbuyAnGkiQ)
    * [Creating Managed Instance Group Templates](https://www.youtube.com/watch?v=bpf230Gdrv4)

#### **Creating a new instance template**

```bash
gcloud compute instance-templates create INSTANCE_TEMPLATE_NAME
```
    If you do not provide explicit template settings, gcloud compute uses the following default values:
    - Machine type: n1-standard-1
    - Image: The latest Debian image
    - Boot disk: A new standard boot disk named after the instance
    - Network: The default VPC network
    - IP address: An ephemeral external IP address
    
#### **Creating an instance template with a container image**
    You can specify a container image in an instance template. By default, Compute Engine also includes in the template a Container-Optimized OS image with Docker installed
```bash
 gcloud compute instance-templates create-with-container nginx-vm \
     --container-image gcr.io/cloud-marketplace/google/nginx1:1.12
```
#### **Creating an instance template that specifies a subnet**
    The following example creates a template called template-qa that only creates instances in the subnet-us-qa subnet.
```bash
gcloud compute instance-templates create template-qa \
    --region us-central1 \
    --subnet subnet-us-qa
```
#### **Getting information about an instance template**
```bash
gcloud compute instance-templates describe [INSTANCE_TEMPLATE_NAME]
```
#### **Listing instance templates**
```bash
gcloud compute instance-templates list
```
#### **Deleting an instance template**
```bash
gcloud compute instance-templates delete 
[INSTANCE_TEMPLATE_NAME]
```
#### **Creating a managed instance group**
    You can create two types of managed instance groups:
    * A zonal managed instance group, which contains instances from the same zone.
    * A regional managed instance group, which contains instances from multiple zones across the same region.

```bash
gcloud compute instance-groups managed create example-group \
    --base-instance-name test \
    --size 3 \
    --template an-instance-template
```
#### **Deleting a managed instance group**
```bash
gcloud compute instance-groups managed delete INSTANCE_GROUP_NAME \
    --zone ZONE
```
---
### 3.1.3.- Generating/uploading a custom SSH key for instances
- Doc References
    * [Managing SSH keys in metadata](https://cloud.google.com/compute/docs/instances/adding-removing-ssh-keys)
    * [How to add the public SSH key to a GCP Virtual Machine](https://souvikhaldar.medium.com/how-to-add-the-public-ssh-key-to-a-gcp-virtual-machine-ef5703e8e596)
    * [How to get the ssh keys for a new Google Compute Engine instance?](https://stackoverflow.com/questions/27535945/how-to-get-the-ssh-keys-for-a-new-google-compute-engine-instance)
- Video
    * [Managing SSH Keys](https://www.youtube.com/watch?v=Z_ePcvnjQb4)

#### **Permissions required for this task**
* __compute.instances.setMetadata__ on the instance if setting metadata on the instance
* __compute.projects.setCommonInstanceMetadata__ on the project if setting project-wide metadata
* __iam.serviceAccounts.actAs__ on the project if setting project-wide metadata

### **Creating a new SSH key**
```bash
ssh-keygen -t rsa -f ~/.ssh/[KEY_FILENAME] -C [USERNAME]

[KEY_FILENAME]: the name that you want to use for your SSH key files. For example, a filename of my-ssh-key generates a private key file named my-ssh-key and a public key file named my-ssh-key.pub.
[USERNAME]: the name of the user connecting to the VM. For example, cloudysanfrancisco@gmail.com or cloudysanfrancisco
```

#### **Adding or removing project-wide public SSH keys**
```bash
gcloud compute project-info describe
...
metadata:
  fingerprint: QCofVTHlggs=
  items:
  - key: ssh-keys
    value: |-
      [USERNAME_1]:ssh-rsa [EXISTING_KEY_VALUE_1] [USERNAME_1]
      [USERNAME_2]:ssh-rsa [EXISTING_KEY_VALUE_2] [USERNAME_2]
...

gcloud compute project-info add-metadata \ 
--metadata-from-file ssh-keys=[LIST_PATH]
```
---
### 3.1.4.- Configuring a VM for Stackdriver monitoring and logging
- Doc References
    * [Quickstart for monitoring a Compute Engine instance](https://cloud.google.com/monitoring/quickstart-lamp)
- Video
- * [Installing Stackdriver Monitoring Agent on VM Instance](https://www.youtube.com/watch?v=jG-lTxzgC10)
---
### 3.1.5.- Assessing compute quotas and requesting increases

- Doc References
* [Resource quotas in Compute Engine](https://cloud.google.com/compute/quotas?hl=es-419)
* [Increase quota](https://helpcenter.itopia.com/en/articles/2565547-increase-compute-engine-quotas-in-gcp)
*[How Increase quota](https://www.hex64.net/how-to-increase-quota-of-resources-in-google-cloud-platform/)
- Video
* [Setting up cost controls with quota](https://www.youtube.com/watch?v=XpSBBFSBM9g)
---
### 3.1.6.- Installing the Stackdriver Agent for monitoring and logging
- Video
    * [Stackdriver Agent Install](https://www.youtube.com/watch?v=vZNR4wYxHYY)

- Doc References
    * [Installing the Cloud Monitoring agent on a single VM](https://cloud.google.com/monitoring/agent/installation#agent-install-debian-ubuntu)
    * [Installing the Cloud Logging agent on a single VM](https://cloud.google.com/logging/docs/agent/installation)
