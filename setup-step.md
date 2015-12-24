### etcd cluster

* reference document

> https://coreos.com/etcd/docs/latest/clustering.html

* public etcd discovery

|ip |
|---|
|10.113.232.251  dev-kube001.ncl.nhnsystem.com dev-kube001.ncl|
|10.113.232.215	 dev-kube002.ncl.nhnsystem.com dev-kube002.ncl|
|10.113.233.143  dev-kube003.ncl.nhnsystem.com dev-kube003.ncl|
|10.113.233.108  dev-kube004.ncl.nhnsystem.com dev-kube004.ncl|

```
[irteamsu@dev-kube001.ncl ~]$ curl https://discovery.etcd.io/new?size=4
https://discovery.etcd.io/0128c2d484d36402abafb011e91284ce
```
```
[irteamsu@dev-kube001.ncl ~]$ ETCD_DISCOVERY=https://discovery.etcd.io/0128c2d484d36402abafb011e91284ce
```
```
[irteamsu@dev-kube001.ncl ~]$ etcd -name kube001 \
 -initial-advertise-peer-urls http://10.113.232.251:2380 \
 -listen-peer-urls http://10.113.232.251:2380 \
 -listen-client-urls http://10.113.232.251:2379,http://127.0.0.1:2379 \
 -advertise-client-urls http://10.113.232.251:2379 \
 -discovery https://discovery.etcd.io/0128c2d484d36402abafb011e91284ce
 ```
 ```
 [irteamsu@dev-kube001.ncl ~]$ etcd -name kube001 \
  -initial-advertise-peer-urls http://10.113.232.215:2380 \
  -listen-peer-urls http://10.113.232.215:2380 \
  -listen-client-urls http://10.113.232.215:2379,http://127.0.0.1:2379 \
  -advertise-client-urls http://10.113.232.215:2379 \
  -discovery https://discovery.etcd.io/0128c2d484d36402abafb011e91284ce
  ```
  ```
  [irteamsu@dev-kube001.ncl ~]$ etcd -name kube001 \
   -initial-advertise-peer-urls http://10.113.233.143:2380 \
   -listen-peer-urls http://10.113.233.143:2380 \
   -listen-client-urls http://10.113.233.143:2379,http://127.0.0.1:2379 \
   -advertise-client-urls http://10.113.233.143:2379 \
   -discovery https://discovery.etcd.io/0128c2d484d36402abafb011e91284ce
   ```
   ```
   [irteamsu@dev-kube001.ncl ~]$ etcd -name kube001 \
    -initial-advertise-peer-urls http://10.113.233.108:2380 \
    -listen-peer-urls http://10.113.233.108:2380 \
    -listen-client-urls http://10.113.233.108:2379,http://127.0.0.1:2379 \
    -advertise-client-urls http://10.113.233.108:2379 \
    -discovery https://discovery.etcd.io/0128c2d484d36402abafb011e91284ce
    ```
