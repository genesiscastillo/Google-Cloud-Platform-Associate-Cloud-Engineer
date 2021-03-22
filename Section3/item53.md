# 3.-  Deploying and implementing a cloud solution

## 3.5.- Deploying and implementing networking resources
---
### 3.5.3.- Creating ingress and egress firewall rules for a VPC

- Video : [Protect Your Google Cloud Instances with Firewall Rules](https://www.youtube.com/watch?v=HTVV9YzGw5k)

```bash
gcloud compute firewall-rules create NAME \
    [--network NETWORK; default="default"] \
    [--priority PRIORITY;default=1000] \
    [--direction (ingress|egress|in|out); default="ingress"] \
    [--action (deny | allow )] \
    [--target-tags TAG[,TAG,...]] \
    [--target-service-accounts=IAM_SERVICE_ACCOUNT[,IAM_SERVICE_ACCOUNT,...]] \
    [--source-ranges CIDR_RANGE[,CIDR_RANGE,...]] \
    [--source-tags TAG,TAG,] \
    [--source-service-accounts=IAM_SERVICE_ACCOUNT[,IAM_SERVICE_ACCOUNT,...]] \
    [--destination-ranges CIDR_RANGE[,CIDR_RANGE,...]] \
    [--rules (PROTOCOL[:PORT[-PORT]],[PROTOCOL[:PORT[-PORT]],...]] | all ) \
    [--disabled | --no-disabled] \
    [--enable-logging | --no-enable-logging] \
    [--logging-metadata LOGGING_METADATA]
```

**[--direction=DIRECTION]**

    If direction is NOT specified, then default is to apply on incoming traffic. For incoming traffic, it is NOT supported to specify destination-ranges; For outbound traffic, it is NOT supported to specify source-ranges or source-tags.

    For convenience, 'IN' can be used to represent ingress direction and 'OUT' can be used to represent egress direction.

        IRECTION must be one of: INGRESS, EGRESS, IN, OUT.


- IP subnets
    **[--source-ranges=CIDR_RANGE,[CIDR_RANGE,…]]**

    A list of IP address blocks that are allowed to make inbound connections that match the firewall rule to the instances on the network. The IP address blocks must be specified in [CIDR format](http://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing).

    If neither __--source-ranges__ nor __--source-tags__ are specified, __--source-ranges__ defaults to 0.0.0.0/0, which means that the rule applies to all incoming connections from inside or outside the network. If both __--source-ranges__ and __--source-tags__ are specified, the rule matches if either the range of the source matches __--source-ranges__ or the tag of the source matches __--source-tags__.

    If neither __--source-ranges__ nor __--source-tags__ is provided, then this flag will default to 0.0.0.0/0, allowing all sources. Multiple IP address blocks can be specified if they are separated by commas.

    **[--destination-ranges=CIDR_RANGE,[CIDR_RANGE,…]]**

    The firewall rule will apply to traffic that has destination IP address in these IP address block list. The IP address blocks must be specified in [CIDR format](http://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing).

    If __--destination-ranges__ is NOT provided, then this flag will default to 0.0.0.0/0, allowing all destinations. Multiple IP address blocks can be specified if they are separated by commas.

- Tags

    **[--source-tags=TAG,[TAG,…]]**

    A list of instance tags indicating the set of instances on the network to which the rule applies if all other fields match. 
    
    If neither __--source-ranges__ nor __--source-tags__ are specified, __--source-ranges__ defaults to 0.0.0.0/0, which means that the rule applies to all incoming connections from inside or outside the network.

    If both __--source-ranges__ and __--source-tags__ are specified, an inbound connection is allowed if either the range of the source matches __--source-ranges__ or the tag of the source matches __--source-tags__.

    Tags can be assigned to instances during instance creation.

    If source tags are specified then neither a source nor target service account can also be specified.


    **[--target-tags=TAG,[TAG,…]]**

    A list of instance tags indicating the set of instances on the network which may accept inbound connections that match the firewall rule. If both target tags and target service account are omitted, all instances on the network can receive inbound connections that match the rule.

    Tags can be assigned to instances during instance creation.

    If target tags are specified then neither a source nor target service account can also be specified.

- Service accounts

    **[--source-service-accounts=EMAIL,[EMAIL,…]]**

    The email of a service account indicating the set of instances on the network which match a traffic source in the firewall rule.

    If a source service account is specified then neither source tags nor target tags can also be specified.

    **[--target-service-accounts=EMAIL,[EMAIL,…]]**

    The email of a service account indicating the set of instances to which firewall rules apply. If both target tags and target service account are omitted, the firewall rule is applied to all instances on the network.

    If a target service account is specified then neither source tag nor target tags can also be specified.
