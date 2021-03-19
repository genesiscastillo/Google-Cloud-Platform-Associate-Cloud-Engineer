add notes# 3.-  Deploying and implementing a cloud solution

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

---
### 3.1.3.- Generating/uploading a custom SSH key for instances
---
### 3.1.4.- Configuring a VM for Stackdriver monitoring and logging
---
### 3.1.5.- Assessing compute quotas and requesting increases

---
### 3.1.6.- Installing the Stackdriver Agent for monitoring and logging
