# 1.- Setting up a cloud solution environment

## 1.1.- Setting up cloud projects and accounts

### 1.1.1.- Creating projects

---
	* ADMINISTRACION DE RECURSOS 

	* PROYECTOS
---

#### ADMINISTRACION DE RECURSOS - ORGANIZACION / FOLDER / PROYECTOS

* Docs References

    - [Creating and managing organizations](https://cloud.google.com/resource-manager/docs/creating-managing-organization)

    - [Creating and managing Folders](https://cloud.google.com/resource-manager/docs/creating-managing-folders)

* Videos References

    - [VIDEO 1](https://www.youtube.com/watch?v=jIYEDt3wdrk)

    - [VIDEO 2](https://www.youtube.com/watch?v=NOOhDq1JyIM)

* Commands

    - [organizations](https://cloud.google.com/sdk/gcloud/reference/organizations)
    - [resources-manager](https://cloud.google.com/sdk/gcloud/reference/resource-manager)

* Comandos Comunes

    *siendo organization_id = 123456*

```bash
    gcloud organizations list

    gcloud resource-manager folders create facturacion --display-name="Area Facturacion" --organization=123456

    gcloud resource-manager folders list --organization=123456

    gcloud resource-manager folders create ambulatorio --display-name="Sector Ambulatorio" --folder=facturacion

    gcloud resource-manager folders list --folder=facturacion

    gcloud resource-manager folders add-iam-policy-binding facturacion --member=user:juanito@gmail.com --role=role/viewer
```
---
#### PROJECTO
---

* Permissions to create project

    - *resourcemanager.projects.create*

        - [other permission](https://cloud.google.com/resource-manager/docs/access-control-proj#permissions_and_roles)

* Role

    - *roles/resourcemanager.projectCreator*

        - [predefined roles](https://cloud.google.com/resource-manager/docs/access-control-proj#using_predefined_roles)

* Sample Creating Project

    - [Doc Reference](https://cloud.google.com/resource-manager/docs/creating-managing-projects)

```bash
gcloud projects create example-foo-bar-1 --name="Happy project"  --labels="type=happy"

gcloud projects list

gcloud projects update example-foo-bar-1 --name="Foo Bar & Grill"

gcloud projects list

gcloud projects describe sign-in-21-ccf

gcloud projects delete example-foo-bar-1 

gcloud proyects undelete example-foo-bar-1 

```
---
#### QUESTIONS
---
*You have been asked to list the name of active account using gcloud CLI. Which of the following command will you use?*

    A. gcloud config list  
    B. gcloud auth list  
    C. gcloud account list  
    D. gcloud project list

*Your teammate launched 3 instances using gcloud compute instances create command with all the required flags. After few mins, you checked the console and found 0 instances in the GCE virtual machine section. How would you identify the project against which the command executed?*

    A. gcloud auth application-default  
    B. gcloud projects list  
    C. gcloud debug  
    D. gcloud config list

*Your company has been working on an application for the last three months and is now ready to roll out the same to the UAT environment for beta testing. Your manager has asked you to create a replica of dev project. Which is the best way to clone/replicate the existing project?*

    A. Go to Manage resources under IAM & admin section, select the project you want to clone and click on the Clone button on top.  
    B. Go to the dashboard, click on three vertical dots within Project info and click Clone Project.  
    C. Execute gcloud command: 
	    gcloud project clone-project --source Eazeteachs-dev-prj --destination Eazeteachs-uat-prj.  
    D. None of the above.

*What is the correct command to create an IAM user using Google Cloud CLI?*

    A. gcloud iam create --name “[email protected]” --role “roles/editor”  
    B. gcloud iam create-user --name “[email protected]” --role “roles/editor”  
    C. gcloud projects add-iam-policy-binding Eazeteachs-prj --member “user:[email protected]” --role “roles/editor”
    D. gcloud projects add-iam-user-binding Eazeteachs-prj --member “user:[email protected]” --role “roles/editor”

*Your colleague has asked for help in creating an IAM role using Google Cloud
 CLI. Which of the following is the correct command to create an IAM role?*

    A. gcloud iam create role viewer-role --project Eazeteachs-prj --permissions “roles/viewer”  
    B. gcloud iam roles create viewer-role --project Eazeteachs-prj --permissions “roles/viewer”  
    C. gcloud iam roles create viewer-role --project Eazeteachs-prj --file role-definition.yaml  
    D. gcloud project roles create --type iam viewer-role --project Eazeteachs-prj --file role-definition.yaml

*You work in a small company where everyone should be able to view all resources of a specific project. You want to grant them access following Google’s recommended practices. What should you do?*

    A. Create a script that uses "gcloud projects add-iam-policy-binding" for all users’ email addresses and the Project Viewer role.  
    B. Create a script that uses "gcloud iam roles create" for all users’ email addresses and the Project Viewer role.  
    C. Create a new Google Group and add all users to the group. Use "gcloud projects add-iam-policy-binding" with the Project Viewer role and Group email address.
    D. Create a new Google Group and add all members to the group. Use "gcloud iam roles create" with the Project Viewer role and Group email address.

---