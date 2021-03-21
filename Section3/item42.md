

# 3.-  Deploying and implementing a cloud solution

## 3.4.- Deploying and implementing data solutions

### 3.4.2.- Loading data
#### Command line upload
- Cloud Storage
```bash
    gsutil cp OBJECT_LOCATION gs://DESTINATION_BUCKET_NAME/
```
- VM Compute Engine
```bash
gcloud compute scp local-file-path instance-name:~

gcloud compute scp --recurse instance-name:remote-dir local-dir
```
#### API transfer
What is Storage Transfer Service?
Storage Transfer Service is a product that enables you to:
- Move or backup data to a Cloud Storage bucket either from other cloud storage providers or from your on-premises storage.
- Move data from one Cloud Storage bucket to another, so that it is available to different groups of users or applications.
- Periodically move data as part of a data processing pipeline or analytical workflow.

Storage Transfer Service provides options that make data transfers and synchronization easier. For example, you can:
- Schedule one-time transfer operations or recurring transfer operations.
- Delete existing objects in the destination bucket if they don't have a corresponding object in the source
- Delete data source objects after transferring them.
- Schedule periodic synchronization from a data source to a data sink with advanced filters based on file creation dates, file-names, and the times of day you prefer to import data.

Storage Transfer Service does the following by default:
- Storage Transfer Service copies a file from the data source if the file doesn't exist in the data sink or if it differs between the version in the source and the sink.
- Retains files in the source after the transfer operation.
- Uses TLS encryption for HTTPs connections. The only exception is if you specify an HTTP URL for a URL list transfer.


#### Import / export

- Exporting and Importing Entities (Datastore)
    * Exporting all entities
    ```bash
     gcloud datastore export gs://bucket-name --async
    ```
    * Importing all entities
    ```bash
    gcloud datastore import gs://bucket-name/file-path/file-name.overall_export_metadata --async
    ```

#### load data from Cloud Storage
- Upload your existing MySQL database to Google Cloud Storage
```script
mysqldump --databases database_name [-h instance-ip -u username -p password] \
--hex-blob --default-character-set=utf8 > database_file.sql
```

#### streaming data to Cloud Pub/Sub

The following streaming templates export Pub/Sub data to different destinations:
- Pub/Sub Subscription to BigQuery
- Pub/Sub to Pub/Sub relay
- Pub/Sub to Cloud Storage Avro
- Pub/Sub to Cloud Storage Text
- Cloud Storage Text to Pub/Sub (Batch)
- Storage Text to Pub/Sub (Stream)
    * [Crear Template](https://github.com/GoogleCloudPlatform/DataflowTemplates) 
```bash
mvn compile exec:java \
-Dexec.mainClass=com.google.cloud.teleport.templates.TextToPubsubStream \
-Dexec.args="\
--project=${PROJECT_ID} \
--stagingLocation=gs://${STAGING_BUCKET}/dataflow/pipelines/${PIPELINE_FOLDER}/staging \
--tempLocation=gs://${STAGING_BUCKET}/dataflow/pipelines/${PIPELINE_FOLDER}/temp \
--runner=DataflowRunner \
--inputFilePattern=gs://path/to/*.csv \
--outputTopic=projects/${PROJECT_ID}/topics/${TOPIC_NAME}"
```

* [Text Files on Cloud Storage to Pub/Sub (Stream)](https://cloud.google.com/dataflow/docs/guides/templates/provided-streaming#text-files-on-cloud-storage-to-pubsub-stream)
    - Requirements for this pipeline:

        * Input files must be in newline-delimited JSON or CSV format. Records that span multiple lines in the source files can cause issues downstream, as each line within the files will be published as a message to Pub/Sub.
            * The Pub/Sub topic must exist prior to execution.
            * The pipeline runs indefinitely and needs to be terminated manually.


```bash
gcloud dataflow jobs run JOB_NAME \
--gcs-location gs://YOUR_BUCKET_NAME/templates/MyTemplate \
--parameters \
inputFile=gs://YOUR_BUCKET_NAME/input/my_input.txt,\
outputFile=gs://YOUR_BUCKET_NAME/output/my_output

or 

gcloud dataflow jobs run JOB_NAME \
--gcs-location gs://dataflow-templates-REGION/latest/Stream_GCS_Text_to_Cloud_PubSub \
--region REGION\
--staging-location TEMP_LOCATION\
--parameters \
inputFilePattern=gs://BUCKET_NAME/FILE_PATTERN,\
outputTopic=projects/PROJECT_ID/topics/TOPIC_NAME
```

###### other example
```bash
gcloud dataflow jobs list --region=us-central1

gcloud dataflow jobs describe 2020-07-07_12_28_18-12115131109562943692  --region=us-central1

gcloud dataflow jobs show 2020-07-07_12_28_18-12115131109562943692 --region=us-central1

gcloud dataflow sql query "SELECT first_name FROM bigquery.table.`fal-retail-dtlk-uat`.guille.test_json where last_name='Doe'" --job-name=my-job --region=us-central1 --bigquery-dataset=guille --bigquery-table=my_output_table

gcloud beta dataflow logs list JOB_ID --region=us-central1

```