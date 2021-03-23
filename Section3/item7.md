

# 3.-  Deploying and implementing a cloud solution
## 3.7.- Deploying an Application using Deployment Manager

- [Sample Yaml](https://github.com/GoogleCloudPlatform/deploymentmanager-samples/tree/master/examples/v2)

- [Supported resource types](https://cloud.google.com/deployment-manager/docs/configuration/supported-resource-types)

- gcloud services enable compute.googleapis.com deploymentmanager.googleapis.com  

#### Creating a basic template

*vm.yaml*
```yaml
resources:
- name: vm-created-by-deployment-manager
  type: compute.v1.instance
  properties:
    zone: us-central1-a
    machineType: zones/us-central1-a/machineTypes/n1-standard-1
    disks:
    - deviceName: boot
      type: PERSISTENT
      boot: true
      autoDelete: true
      initializeParams:
        sourceImage: projects/debian-cloud/global/images/family/debian-9
    networkInterfaces:
    - network: global/networks/default
```

### 3.7.1.- Developing Deployment Manager templates to automate deployment of an application

```yaml
resources:
- type: compute.v1.instance
  name: quickstart-deployment-vm
  properties:
    # The properties of the resource depend on the type of resource. For a list
    # of properties, see the API reference for the resource.
    zone: us-central1-f
    # Replace [MY_PROJECT] with your project ID
    machineType: https://www.googleapis.com/compute/v1/projects/[MY_PROJECT]/zones/us-central1-f/machineTypes/f1-micro
    disks:
    - deviceName: boot
      type: PERSISTENT
      boot: true
      autoDelete: true
      initializeParams:
        # See a full list of image families at https://cloud.google.com/compute/docs/images#os-compute-support
        # The format of the sourceImage URL is: https://www.googleapis.com/compute/v1/projects/[IMAGE_PROJECT]/global/images/family/[FAMILY_NAME]
        sourceImage: https://www.googleapis.com/compute/v1/projects/debian-cloud/global/images/family/debian-9
    # Replace [MY_PROJECT] with your project ID
    networkInterfaces:
    - network: https://www.googleapis.com/compute/v1/projects/[MY_PROJECT]/global/networks/default
      # Access Config required to give the instance a public IP address
      accessConfigs:
      - name: External NAT
        type: ONE_TO_ONE_NAT
```
*In the configuration file, replace [MY_PROJECT] with your project ID.*

```bash
    gcloud deployment-manager deployments create quickstart-deployment --config vm.yaml

    gcloud deployment-manager deployments list

    gcloud deployment-manager deployments describe quickstart-deployment

    gcloud deployment-manager deployments delete quickstart-deployment

other

    gcloud deployment-manager deployments stop my-deployment
    gcloud deployment-manager deployments stop my-deployment --async
    gcloud deployment-manager deployments stop my-deployment  --fingerprint=deployment-fingerprint

    gcloud deployment-manager deployments update my-deployment

    gcloud deployment-manager deployments cancel-preview my-deployment

other - manifests 
    gcloud deployment-manager manifests list --deployment=my-deployment
    gcloud deployment-manager manifests describe  --deployment=my-deployment manifest-name

other 
    gcloud deployment-manager operations list --simple-list
    gcloud deployment-manager resources list --deployment=my-deployment
    gcloud deployment-manager types list
```
#### Defining Template Properties
*vm_template.jinja*
```yaml
- name: vm-{{ env["deployment"] }}
  type: compute.v1.instance
  properties:
    zone: us-central1-a
    machineType: zones/{{ properties["zone"] }}/machineTypes/n1-standard-1
    disks:
    - deviceName: boot
      type: PERSISTENT
      boot: true
      autoDelete: true
      initializeParams:
        sourceImage: projects/debian-cloud/global/images/family/debian-9
    networkInterfaces:
    - network: global/networks/default
```
```bash
    gcloud deployment-manager deployments create a-single-vm --template vm_template.jinja \
    --properties zone:us-central1-a

```

### 3.7.2 Launching a Deployment Manager template to provision GCP resources and configure an application automatically

#### VM with Startup Script
*vm_template.jinja.schema*
```yaml
info:
  title: VM with startup script
  author: Google Inc.
  description: Creates a VM running the provided startup script.

required:
- zone
- startup-script

properties:
  zone:
    description: Zone to create the resources in.
    type: string

  startup-script:
    description: The startup script to run on VM intialization.
    type: string
```
*vm_template.jinja*
```yaml
{% set NAME_PREFIX = env['deployment'] + '-' + env['name'] %}

resources:
- type: compute.v1.instance
  name: {{ NAME_PREFIX }}-vm
  properties:
    zone: {{ properties["zone"] }}
    machineType: https://www.googleapis.com/compute/v1/projects/{{ env["project"] }}/zones/{{ properties["zone"] }}/machineTypes/f1-micro
    metadata:
      items:
      # For more ways to use startup scripts on an instance, see:
      #   https://cloud.google.com/compute/docs/startupscript
      - key: startup-script
        value: |
          {{ properties["startup-script"]|indent(10) }}
    disks:
    - deviceName: boot
      type: PERSISTENT
      boot: true
      autoDelete: true
      initializeParams:
        diskName: {{ NAME_PREFIX }}-disk
        sourceImage: https://www.googleapis.com/compute/v1/projects/debian-cloud/global/images/family/debian-9

    networkInterfaces:
    - network: https://www.googleapis.com/compute/v1/projects/{{ env["project"] }}/global/networks/default
      # Access Config required to give the instance a public IP address
      accessConfigs:
      - name: External NAT
        type: ONE_TO_ONE_NAT
```
*vm.yaml*
```yaml
imports:
- path: vm_template.jinja

resources:
- name: my-vm
  type: vm_template.jinja
  properties:
    zone: ZONE_TO_RUN
    startup-script: |
      #!/bin/bash
      python -m SimpleHTTPServer 8080
```
```bash
    gcloud deployment-manager deployments create vm-startup-script --config vm.yaml

    gcloud compute instances describe my-vm-vm | grep "natIP"
```

#### other example

[Custom IAM Role](https://github.com/GoogleCloudPlatform/deploymentmanager-samples/tree/master/examples/v2/iam_custom_role)

*project_custom_role.jinja.schema*
```yaml
info:
  title: Cloud IAM Project Level Custom Roles
  description: Creates a custom role under the gcloud default project.

imports:
  - path: project_custom_role.jinja

properties:
  title:
    type: string
    default: "\"\""
    description: The title of the custom role.

  description:
    type: string
    default: "\"\""
    description: A description of the custom role.

  stage:
    type: string
    default: ALPHA
    description: The current launch stage of the custom role.
    enum:
     - ALPHA
     - BETA
     - GA
     - DEPRECATED
     - DISABLED
     - EAP

  includedPermissions:
    type: array
    default: []
    description: The permissions that this custom role includes.
```
*project_custom_role.jinja*
```yaml
  resources:
  - name: custom-role
    type: gcp-types/iam-v1:projects.roles
    properties:
      parent: projects/{{ env["project"] }}
      roleId: {{ properties["roleId"] }}
      role:
        title: {{ properties["title"] }}
        description: {{ properties["description"] }}
        stage: {{ properties["stage"] }}
        includedPermissions: {{ properties["includedPermissions"] }}
```
*project_custom_role.yaml*
```yaml
imports:
- path: project_custom_role.jinja

resources:
- name: custom-role
  type: project_custom_role.jinja
  properties:
    roleId: aCustomRole
    title: My Title
    description: My description.
    includedPermissions:
    - iam.roles.get
    - iam.roles.list
```
```bash
    gcloud deployment-manager deployments create YOUR_DEPLOYMENT_NAME --config project_custom_role.yaml
```