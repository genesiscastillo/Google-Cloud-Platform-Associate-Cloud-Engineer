# Otros Recursos


## Cloud Run

![Cloud Run](https://cloud.google.com/kuberun/docs/images/choose-platform.svg?hl=es-419)

### Cloud Run (fully managed)
The Cloud Run (fully managed) platform allows you to deploy stateless containers without having to worry about the underlying infrastructure. Your workloads are automatically scaled out or in to zero depending on the traffic to your app. You only pay when your app is running, billed to the nearest 100 milliseconds.

### Cloud Run for Anthos
Cloud Run for Anthos abstracts away complex Kubernetes concepts, allowing developers to easily leverage the benefits of Kubernetes and serverless together. It provides access to custom machine types, additional networking support, and Cloud Accelerators. It allows you to run your workloads on-premises or on Google Cloud.


## Cloud KMS - Cloud Key Management Service

### Key rings and keys
To encrypt and decrypt content you will need a Cloud KMS key, which is part of a key ring

```bash
#Create a __key ring__ named *test*, and a __key__ named *quickstart*. 
#Refer to the object hierarchy overview for more information about these objects and how they are related.

gcloud kms keyrings create "test" \
    --location "global"

gcloud kms keys create "quickstart" \
    --location "global" \
    --keyring "test" \
    --purpose "encryption"

#You can use the list option to view the name and metadata for the key that you just created.

gcloud kms keys list \
    --location "global" \
    --keyring "test"
```
NAME                                                                      |PURPOSE|          PRIMARY_STATE
---|---|---
projects/project-id/locations/global/keyRings/test/cryptoKeys/quickstart|  ENCRYPT_DECRYPT|  ENABLED

### Encrypt data

```bash
echo -n "Some text to be encrypted" > mysecret.txt

gcloud kms encrypt \
    --location "global" \
    --keyring "test" \
    --key "quickstart" \
    --plaintext-file ./mysecret.txt \
    --ciphertext-file ./mysecret.txt.encrypted
```

### Decrypt ciphertext
```bash
gcloud kms decrypt \
    --location "global" \
    --keyring "test" \
    --key "quickstart" \
    --ciphertext-file ./mysecret.txt.encrypted \
    --plaintext-file ./mysecret.txt.decrypted
```

### Clean up
```bash
gcloud kms keys versions list \
    --location "global" \
    --keyring "test" \
    --key "quickstart"

gcloud kms keys versions destroy key-version \
    --location "global" \
    --keyring "test" \
    --key "quickstart"
```
### Using Encryption Keys in Cloud Storage
[AQUI LA NOTA](https://www.facebook.com/story.php?story_fbid=3792750050761996&id=797730803597284)

gsutil accepts CSEKs for interacting with Cloud Storage objects using the JSON API. The keys are provided via the .boto configuration file like so:

    [GSUtil]
    encryption_key = projects/PROJECT_ID/locations/LOCATION/keyRings/KEYRING/cryptoKeys/KEYNAME
    decryption_key1 = ...
    decryption_key2 = ...

```bash
gsutil -o 'GSUtil:encryption_key=projects/PROJECT_ID/locations/LOCATION/keyRings/KEYRING/cryptoKeys/KEYNAME' \
       cp /some/local/file gs://my-bucket/
```
