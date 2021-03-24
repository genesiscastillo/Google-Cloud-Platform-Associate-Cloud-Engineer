# 4.- Ensuring successful operation of a cloud solution
## 4.1.- Managing Compute Engine resources
----
## 4.3- Managing App Engine resources
---
### 4.3.1.- Adjusting application traffic splitting parameters

**Splitting Traffic** [doc](https://cloud.google.com/appengine/docs/standard/java/splitting-traffic)

**Traffic splitting** is applied to URLs that do not explicitly target a version. For example, the following URLs split traffic because they target all the available versions within the specified service:

- https://PROJECT_ID.REGION_ID.r.appspot.com - Distributes traffic to versions of the default service.
- https://SERVICE_ID-dot-PROJECT_ID.REGION_ID.r.appspot.com - Distributes traffic to versions of the [SERVICE_ID] service.

```bash
gcloud app services set-traffic [MY_SERVICE] --splits [MY_VERSION1]=[VERSION1_WEIGHT],[MY_VERSION2]=[VERSION2_WEIGHT] --split-by [IP_OR_COOKIE]
```

**Migrating Traffic** [doc](https://cloud.google.com/appengine/docs/standard/java/migrating-traffic)

**Traffic migration** switches the request routing between the versions within a service of your application, moving traffic from one or more versions to a single new version.

```bash
gcloud app services set-traffic [MY_SERVICE] --splits [MY_VERSION]=1
```

---
### 4.3.2.- Setting scaling parameters for autoscaling instances

- [Scaling Google App Engine to No Instances](https://medium.com/google-cloud/scaling-google-app-engine-to-no-instances-or-maybe-just-1-37be4e8d4230)

- [App ref](https://cloud.google.com/appengine/docs/standard/java/config/appref)
```xml
<appengine-web-app xmlns="http://appengine.google.com/ns/1.0">
  <application>simple-app</application>
  <module>default</module>
  <version>uno</version>
  <threadsafe>true</threadsafe>
  <instance-class>F2</instance-class>
  <automatic-scaling>
    <target-cpu-utilization>0.65</target-cpu-utilization>
    <min-instances>5</min-instances>
    <max-instances>100</max-instances>
    <max-concurrent-requests>50</max-concurrent-requests>
  </automatic-scaling>
</appengine-web-app>
```
**\<automatic-scaling>**

Optional. Automatic scaling is assumed by default with a default instance class of F1 unless specified otherwise.

The automatic_scaling element sets minimum and maximum levels for number of instances, latency, and concurrent connections for a module.

This element can contain the following elements:

* \<target-cpu-utilization>\
* \<target-throughput-utilization>\
* \<max-instances>\
* \<min-instances>\
* \<max-concurrent-requests>\
* \<max-idle-instances>\
* \<max-pending-latency>\
* \<min-idle-instances>\
* \<min-pending-latency>

---
### 4.3.3.- Working with management interfaces
- Cloud Console
- Cloud Shell
- Cloud SDK

