# 1.- Setting up a cloud solution environment

## 1.1.- Setting up cloud projects and accounts

### 1.1.4.- Enabling APIs within projects

* Doc Reference
    - [Overview](https://cloud.google.com/service-usage/docs/overview)
    - [services](https://cloud.google.com/docs/overview/cloud-platform-services)
    - [Resumen de cada servicio](https://cloud.google.com/terms/services)

* Nota
    - [Services por default](https://cloud.google.com/service-usage/docs/enabled-service#default)


NAME                              | TITLE
---|---
*bigquery.googleapis.com*           | BigQuery API
*bigquerystorage.googleapis.com*    | BigQuery Storage API
*cloudapis.googleapis.com*          | Google Cloud APIs
*clouddebugger.googleapis.com*      | Cloud Debugger API
*cloudtrace.googleapis.com*         | Cloud Trace API
*datastore.googleapis.com*          | Cloud Datastore API
*logging.googleapis.com*            | Cloud Logging API
*monitoring.googleapis.com*         | Cloud Monitoring API
*servicemanagement.googleapis.com*  | Service Management API
*serviceusage.googleapis.com*       | Service Usage API
*sql-component.googleapis.com*      | Cloud SQL
*storage-api.googleapis.com*        | Google Cloud Storage JSON API
*storage-component.googleapis.com*  | Cloud Storage
*storage.googleapis.com*            | Cloud Storage API

---
* Sample

```bash
gcloud services list

gecloud services list --avalaible

gcloud services enabled compute.googleapis.com 

gcloud services diabled compute.googleapis.com s
```
---
#### Questions

*Which command will let you enable Google Compute service using gcloud CLI?*

    A. gcloud enable compute  
    B. gcloud service enable compute  
    C. gcloud service compute enable  
    D. gcloud services enable compute
---

