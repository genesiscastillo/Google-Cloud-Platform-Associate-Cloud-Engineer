# 1.- Setting up a cloud solution environment

## 1.1.- Setting up cloud projects and accounts

### 1.1.2.- Assigning users to pre-defined IAM roles within a project

* Doc References

    - [IAM Roles Explained](https://medium.com/google-cloud/gcp-iam-roles-explained-af84955346e7)
    - [Understanding  Roles](https://cloud.google.com/iam/docs/understanding-roles)

* Videos References
    - [IAM Roles](https://www.youtube.com/watch?v=Sdt-i-Q7tyA)
    - [Using Permissions](https://www.youtube.com/watch?v=ZWKq5YzIAec)

* Comandos Comunes

```bash
gcloud projects get-iam-policy example-foo-bar-1

gcloud projects add-iam-policy-binding example-foo-bar-1 --member="user:juanito@gmail.com" --role="roles/cloudbuild.builds.builder"

gcloud projects get-iam-policy example-foo-bar-1

gcloud projects set-iam-policy example-foo-bar-1 policy.json / poolicy.yaml
'user:test-user@gmail.com' --role='roles/editor'

gcloud projects remove-iam-policy-binding example-foo-bar-1 --member='user:test-user@gmail.com' --role='roles/editor'

gcloud projects get-iam-policy example-foo-bar-1
```

