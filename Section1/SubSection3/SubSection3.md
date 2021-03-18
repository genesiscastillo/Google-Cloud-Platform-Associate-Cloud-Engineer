# 1.- Setting up a cloud solution environment

## 1.3.- Installing and configuring the command line interface (CLI), specifically the Cloud SDK (e.g., setting the default project)
---
* Doc References
    - [Ques es gcloud](https://cloud.google.com/sdk/gcloud)
    - [Como Instalar SDK Google Cloud (gcloud)](https://cloud.google.com/sdk/docs/install)
    - [Managing SDK Componentes](https://cloud.google.com/sdk/docs/components)

* Video
    - [How to gcloud](https://www.youtube.com/watch?v=j274vq9a2Rs)
---
#### Instalacion de componentes
> [Components Install](https://www.youtube.com/watch?v=Hh8JjaEFhHQ)

    ```bash
    gcloud components list
    gcloud components install <name component>
    gcloud components update <name component>
    ```
#### 3 tecnicas de crear configuracion
- metodo 1 - configuration create
    ```bash
	gcloud config configuration create config-sodimac
	gcloud config configuration activate config-sodimac
	gcloud config set core/account ccastillof@sodimac.cl

	gcloud config configuration create sign-in-21-ccf
	gcloud config configuration activate sign-in-21-ccf
	gcloud config set core/account genesiscastillof@gmail.com
	
	gcloud config --configuation=sign-in-21-ccf list
	gcloud config configurations describe sign-in-21-ccf
	
	gcloud auth login
	```
- metodo 2 - init
	```bash
	gcloud init
	```
- metodo 3 - metodo manual
    ```bash
	gcloud info
	copiar la carpeta \gcloud\configurations\config_default 
    ```
---
#### Commands References

> [Guia Commands References](https://cloud.google.com/sdk/gcloud/reference/config)

```bash
	gcloud config get-value 

	gcloud config set compute/region us-east4
	gcloud config set compute/zone us-east4-c

	gcloud config unset compute/region
```

```bash
    gcloud config configurations describe sign-in-21-ccf

    gcloud compute instances list --configuration=sodimac-marketplace
```
---
#### GOOGLE_APPLICATION_CREDENTIALS
> [Getting started with authentication](https://cloud.google.com/docs/authentication/getting-started)
```bash
export GOOGLE_APPLICATION_CREDENTIALS="/home/user/Downloads/my-key.json"
```
---
#### Activate service account
> [Guia de uso](https://serverfault.com/questions/848580/how-to-use-google-application-credentials-with-gcloud-on-a-server)

```bash
gcloud auth activate-service-account --key-file=key.json
```
---
#### Invocacion Api Rest
```bash
gcloud auth application-default print-access-token

curl -v -X GET -H "Authorization: Bearer <access_token_here>" https://cloudresourcemanager.googleapis.com/v1/projects/{projectId}

```
> [Uso de API Rest con projects](https://cloud.google.com/resource-manager/reference/rest?hl=es)
```bash
curl -v -X GET -H "Authorization: Bearer ya29.c.Kp0B8wcflvzwR5NKBmrDMm7mcPBrprqGzMyUp41o_Amgz3s2s-mnkwpQjnZ86k4hXec5sq_S9t_Pdbg8AwwQYmpv_s3X__4oUEjImEXx7kl_dnD-kqRypTeGMPpjvQQGzxxxGdfU-ToQKZrHqNMr-2q0unuYT5wqUHX08jeFUuE3C8lQIUP7xMInV56mHuFHAL5NrifedtaKBJJMFfTvSA" https://cloudresourcemanager.googleapis.com/v1/projects

```
---
#### Questions

*Your company has replaced your laptop OS from windows to ubuntu and you installed
a stable release of cloud SDK on your machine however when you run kubectl, you
receive  a error stating "Command kubectl not found".
Which command will you you use to install kubectl on ubuntu?*

    A.- sudo apt install kubectl
    B.- gcloud install kubectl
    C.- sudo yum install kubectl
    D.- gcloud components install kubectl

---
*You have been asked to list the active account using gcloud CLI.
Which of the following command will you use?*

    A.- gcloud config list
    B.- gcloud auth list
    C.- gcloud account list
    D.- gcloud projects list

----
*You teammate launched 3 instances using gcloud compute instances create command 
with all the required  flags. After few minutes, you checked the console and 
found 0 instances in the GCE virtual machine section. How would you identify 
the project againts which the command execute?*

    A.- gcloud auth application-default
    B.- gcloud projects list
    C.- gcloud debug
    D.- gcloud config list

----
*What is the gcloud command to set default zone for compute engine server 
using gcloud cli?*

    A.- gcloud config set compute/zone us-east-1a
    B.- gcloud config configurations set compute/zone us-east-1a
    C.- gcloud default set compute/zone us-east-1a

----
#### OTROS RECURSOS

- https://codeburst.io/google-cloud-authentication-by-example-1481b02292e4

- https://www.jhanley.com/google-cloud-understanding-gcloud-configurations/
https://devopscube.com/use-multipl-gcloud-configurations/


