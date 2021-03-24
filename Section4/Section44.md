# 4.- Ensuring successful operation of a cloud solution
## 4.1.- Managing Compute Engine resources
---
## 4.4.- Managing data solutions
---
### 4.4.1.- Executing queries to retrieve data from data instances
- Cloud SQL
- BigQuery
- Cloud Spanner
- Cloud Datastore
- Cloud Bigtable
- Cloud Dataproc
---
### 4.4.2.- Estimating costs of a BigQuery query
---
### 4.4.3.- Backing up and restoring data instances
#### **Cloud SQL**

> [How to Backup Google Cloud SQL for MySQL and Restore on Your Own Server](https://backup.ninja/news/how-backup-google-cloud-sql-mysql-and-restore-your-own-server)

#### **Cloud Datastore**

*SIN INFORMACION*

#### **Cloud Dataproc**

*SIN INFORMACION*

---
### 4.4.4.- Reviewing job status in Cloud Dataproc or BigQuery

#### Dataproc
```bash
gcloud dataproc clusters diagnose cluster-name \
    --region=region \
    ... other args ...

...
Saving archive to cloud
Copying file:///tmp/tmp.FgWEq3f2DJ/diagnostic.tar ...
Uploading   ...23db9-762e-4593-8a5a-f4abd75527e6/diagnostic.tar ...
Diagnostic results saved in:
gs://bucket-name/.../cluster-uuid/.../job-id/diagnostic.tar
    ...


gcloud dataproc clusters describe cluster-name \
    --region=region \
...
  clusterName: cluster-name
  clusterUuid: daa40b3f-5ff5-4e89-9bf1-bcbfec6e0eac
  configuration:
  configurationBucket: dataproc-edc9d85f-...-us
  ...

```
 #### BigQuery
```bash
bq ls -j myproject
bq ls -j -a myproject
bq ls -j --max_creation_time 1539903893000

bq show -j myproject:US.bquijob_123x456_123y123z123c

bq show --format=prettyjson -j myproject:US.bquijob_123x456_789y123z456c

bq --location=location cancel job_id
bq --location=location --nosync cancel job_id
```

---
### 4.4.5.- Moving objects between Cloud Storage buckets
```bash
gsutil cp gs://SOURCE_BUCKET_NAME/SOURCE_OBJECT_NAME gs://DESTINATION_BUCKET_NAME/NAME_OF_COPY

gsutil mv gs://BUCKET_NAME/OLD_OBJECT_NAME gs://BUCKET_NAME/NEW_OBJECT_NAME

gsutil mv gs://SOURCE_BUCKET_NAME/SOURCE_OBJECT_NAME gs://DESTINATION_BUCKET_NAME/DESTINATION_OBJECT_NAME

```
---
### 4.4.6.- Converting Cloud Storage buckets between storage classes

```bash
gsutil rewrite -s STORAGE_CLASS gs://PATH_TO_OBJECT
```

---
### 4.4.7.- Setting object lifecycle management policies for Cloud Storage buckets

#### **Enabling Lifecycle Management**

*config-lifecycle.json*
```json
{
"lifecycle": {
  "rule": [
  {
    "action": {"type": "Delete"},
    "condition": {
      "age": 30,
      "isLive": true
    }
  },
  {
    "action": {"type": "Delete"},
    "condition": {
      "numNewerVersions": 2
    }
  },
  {
    "action": {"type": "Delete"},
    "condition": {
      "age": 35,
      "isLive": false
    }
  }
]
}
}
```
```bash
gsutil lifecycle set [LIFECYCLE_CONFIG_FILE] gs://BUCKET_NAME
```
#### **Disabling Lifecycle Management**

*config-lifecycle-disabled.json*
```json
{
  "lifecycle": {
    "rule": []
  }
}
```
```bash
gsutil lifecycle set [LIFECYCLE_CONFIG_FILE] gs://BUCKET_NAME
```
#### **Checking Lifecycle Configuratio**
```bash
gsutil lifecycle get gs://BUCKET_NAME
```
---
### 4.4.8.- Working with management interfaces
- Cloud Console
- Cloud Shell
- Cloud SDK
