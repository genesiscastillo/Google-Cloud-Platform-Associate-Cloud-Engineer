

# 3.-  Deploying and implementing a cloud solution

## 3.4.- Deploying and implementing data solutions

### 3.4.1.- Initializing data systems with products
---
#### **Cloud SQL**
- Doc References
    * [Creating a MySQL instance](https://cloud.google.com/sql/docs/mysql/create-instance#create-2nd-gen)

```bash
gcloud sql instances create INSTANCE_NAME --cpu=NUMBER_CPUS --memory=MEMORY_SIZE --region=REGION

gcloud sql users set-password root --host=% --instance INSTANCE_NAME --password PASSWORD
```
---
#### **Cloud Datastore**
- Doc References
* [Index Configuration](https://cloud.google.com/datastore/docs/tools/indexconfig)
* [Using the gcloud Tool](https://cloud.google.com/datastore/docs/tools)

*index.yaml*
```yaml
indexes:

- kind: Task
  ancestor: no
  properties:
  - name: done
  - name: priority
    direction: desc

- kind: Task
  properties:
  - name: collaborators
    direction: asc
  - name: created
    direction: desc

- kind: TaskList
  ancestor: yes
  properties:
  - name: percent_complete
    direction: asc
  - name: type
    direction: asc
```

```bash
gcloud datastore indexes create ~/.config/gcloud/emulators/datastore/WEB-INF/index.yaml

gcloud datastore indexes cleanup ~/.config/gcloud/emulators/datastore/WEB-INF/index.yaml
```
```javascript
const datastore = require('@google-cloud/datastore')({
    projectId: 'your-project-id'
});
const entity = {
- kind: TaskList
    key: datastore.key(['TaskList', 5629499534213120, 'TaskItem']),
    data: {
        name: 'Milk',
        completed: false
    }
};
datastore.save(entity, (err) => {
    if (err) {
        console.log('There was an error...', err);
    } else {
        console.log('Saved entity:', entity);
    }
});
```
---
#### **Cloud Bigtable**
```bash
export GOOGLE_APPLICATION_CREDENTIALS="[PATH]"

gcloud components update
gcloud components install cbt

gcloud bigtable instances create quickstart-instance  --display-name="My Instance" --cluster=my-cluster-id  --cluster-zone=us-east1-c
```

- create file */.cbtrc*
    ```properties
    project = project-id
    instance = quickstart-instance
    ```
```bash
cbt createtable my-table

cbt ls

cbt createfamily my-table cf1

cbt ls my-table

cbt set my-table r1 cf1:c1=test-value

cbt read my-table

cbt deletetable my-table

cbt deleteinstance quickstart-instance
```
---
#### **BigQuery**


---
#### **Cloud Spanner**

---
#### **Cloud Pub/Sub**

---
#### **Cloud Dataproc**

---
#### **Cloud Storage**

---
### 3.4.2.- Loading data
- Command line upload
- API transfer
- Import / export
- load data from Cloud Storage
- streaming data to Cloud Pub/Sub

