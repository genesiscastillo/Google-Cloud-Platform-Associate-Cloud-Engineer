# 3.-  Deploying and implementing a cloud solution

## 3.5.- Deploying and implementing networking resources

[Cloud Load Balancing overview](https://cloud.google.com/load-balancing/docs/load-balancing-overview)

![load balancer](https://cloud.google.com/load-balancing/images/lb-simple-overview.svg)


__Global versus regional load balancing__
- Use __global load balancing__ when your backends are distributed across multiple regions, your users need access to the same applications and content, and you want to provide access by using a single anycast IP address. Global load balancing can also provide IPv6 termination.

- Use __regional load balancing__ when your backends are in one region, and you only require IPv4 termination

---
### 3.5.5.- Creating a load balancer to distribute application network traffic to an application

Internal or external | Regional or global | Supported network tiers	| Proxy or pass-through | Traffic type| Load balancer type 
---|---|---|----|---|---
Internal|	Regional|	Premium only|	Pass-through|	TCP or UDP|	Internal TCP/UDP
Internal| Regional|	Premium only	|Proxy	|HTTP or HTTPS	| Internal HTTP(S)
External|	Regional	|Premium or Standard	|Pass-through	|TCP or UDP	|TCP/UDP Network
External|Global in Premium Tier|Premium or Standard|	Proxy	|TCP	|TCP Proxy
External|Effectively regional1 in Standard Tier	|Premium or Standard	|Proxy	|SSL	|SSL Proxy
External|Effectively regional1 in Standard Tier	|Premium or Standard	|Proxy	|HTTP or HTTPS	|External HTTP(S)


#### Global HTTP(S) load balancer

#### Global SSL Proxy load balancer

#### Global TCP Proxy load balancer

#### Regional Network load balancer

#### Regional Internal load balancer

```javascript

    console.log("P E N D I E N T E   D E   R E V I S A R");

```