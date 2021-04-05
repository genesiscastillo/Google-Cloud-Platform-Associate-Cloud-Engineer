# 5.- Configuring access and security

> PENDIENTE

## 5.1.- Managing Identity and Access Management (IAM)
---
### 5.1.1.- Viewing account IAM assignments
---
### 5.1.2.- Assigning IAM roles to accounts or Google Groups
---
### 5.1.3.- Defining custom IAM roles
---
## 5.2.- Managing service accounts
---
### 5.2.1.- Managing service accounts with limited scopes
---
### 5.2.2.- Assigning a service account to VM instances
---
### 5.2.3.- Granting access to a service account in another project
---
## 5.3.- Viewing audit logs for project and managed services


## OTHER RESOURCE - OTHER NOTES

	gcloud iam list-grantable-roles 
	gcloud iam list-testable-permissions
	gcloud iam roles
	gcloud iam service-accounts


# list-grantable-roles
	list IAM grantable roles for a resource [ROLES OTORGADOS]

gcloud iam list-grantable-roles [URI-RESOURCES]
	- The resource can be referenced either via the full resource name or via a URI. 
	- User can then add IAM policy bindings to grant the roles.

# list-testable-permissions
	list IAM testable permissions for a resource [PERMISOS COMPROBABLES]

Ejemplo:
#ALL RESOURCES  
//cloudresourcemanager.googleapis.com/projects/${PROJECT_ID}

#COMPUTE ENGINE
//compute.googleapis.com/projects/[PROJECT_ID]/zones/[ZONE]/instances/[VM_NAME]

#BIGQUERY
//bigquery.googleapis.com/projects/[PROJECT_ID]/datasets/[DATASET_ID]

#STACKDRIVER LOGGING
//logging.googleapis.com/projects/[PROJECT_ID]/logs/cloudbuild


gcloud iam list-grantable-roles //cloudresourcemanager.googleapis.com/projects/sign-in-21-ccf

------------------------
ROLES
A role is a collection of permissions.

#https://cloud.google.com/iam/docs/understanding-roles

TIPOS ROLES
Primitive roles: 
	Roles historically available in the Google Cloud Console. These roles are Owner, Editor, and Viewer. Avoid using these roles if possible, because they include a wide range of permissions across all Google Cloud services.
Predefined roles: 
	Roles that give finer-grained access control than the primitive roles. For example, the predefined role Pub/Sub Publisher [roles/pubsub.publisher] provides access to only publish messages to a Pub/Sub topic.
Custom roles: 
	Roles that you create to tailor permissions to the needs of your organization when predefined roles don’t meet your needs.

	PRIMITIVE ROLES
	roles/viewer
	roles/editor
	roles/owner

		gcloud iam roles describe roles/editor

	PREDEFINED ROLES
	

		gcloud iam roles describe roles/editor

	CUSTOM ROLES
	

gcloud auth revoke --all
gcloud auth login
gcloud config set project sing-in-dev-284714

gcloud iam roles list 

gcloud iam roles list --filter='name: roles/storage.*'

gcloud iam roles describe roles/storage.objectAdmin

--------------------------------------------------------
CREAR 2 ROLES PARA PERSONAL DE AREA DE FACTURACION
ROLE 1 - USUARIO ACCEDE OBTENER LISTAR LOS RECURSOS DE STORAGE
ROLE 2 - SOLO SE ENCARGARA DE ADMINISTRAR EXCLUSIVAMENTE CLOUD STORAGE
---------------------------------------------------------
FACTURARCION USER
	gcloud iam roles create facturacionUser --project=sign-in-21-ccf \
	--title 'Facturacion User' --description 'Facturacion Admin Cloud Storage' \
	--permissions='storage.objects.get,storage.objects.list' --stage GA

	#https://cloud.google.com/iam/docs/understanding-custom-roles?hl=es#testing_and_deploying

gcloud iam roles create facturacionUser --project=sign-in-21-ccf --title='Facturacion User' --description='Facturacion User Cloud Storage' --permissions='storage.objects.get,storage.objects.list' --stage=GA

FACTURARCION ADMMIN

gcloud iam roles create facturacionAdmin --project=sign-in-21-ccf --file=roleFacturacionAdmin.yaml

	name: projects/sign-in-21-ccf/roles/facturacionAdmin

* UPDATE PERMISSIONS 
gcloud iam roles update facturacionAdmin --project=sign-in-21-ccf --file=roleFacturacionAdmin.yaml

* UPDATE STAGE
gcloud iam roles update facturacionUser --project=sign-in-21-ccf --stage DISABLED

* Delete your custom role
gcloud iam roles delete facturacionUser --project=sign-in-21-ccf
 
* Recover your custom role
gcloud iam roles undelete  facturacionUser --project=sign-in-21-ccf

* The role can only be undeleted within 7 days of deletion
-----------------------------------------------------------
TESTING ASSOCIATE ENGINEER

Your project team has asked to disabled a custom role 'editor' from the project
wigth might requiere deletion from your Google Cloud Platform Console.
The project team will inform you when to perform the deletion of the role. 
Suggest the correct gcloud command to perfom the deletion:

A.- gcloud iam roles disable editor --project-id=[PROJECT_ID]
B.- gcloud iam roles update editor --project-id=[PROJECT_ID]
C.- gcloud iam roles update editor --project=[PROJECT_ID]
D.- gcloud iam roles disable-editor --project=[PROJECT-ID]

-------------------------
# https://cloud.google.com/iam/docs/how-to
# https://cloudaffaire.com/how-to-create-a-custom-iam-role-in-gcp/

