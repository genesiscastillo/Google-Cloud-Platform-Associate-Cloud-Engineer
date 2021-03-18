# 1 Setting up a cloud solution environment

## 1.2 Managing billing configuration
---
### 1.2.2.- Linking projects to a billing account
---
* Video
    - [Creacion y Adjuntar](https://www.youtube.com/watch?v=uINleRduCWM)

* Sample Code

```bash
gcloud alpha billing projects link sign-in-21-ccf --billing-account=013693-A5FFB7-359B50
```

```bash
gcloud alpha billing projects unlink sign-in-21-ccf
```

```bash
gcloud alpha billing accounts get-iam-policy 013693-A5FFB7-359B50
```