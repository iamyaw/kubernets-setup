### Pre

* 4 CentOS 7.1 nodes

> uname -a
Linux dev-kube003.ncl 4.3.0-1.el7.elrepo.x86_64 #1 SMP Tue Nov 3 20:15:39 EST 2015 x86_64 x86_64 x86_64 GNU/Linux

| ip |
|----|
|10.113.232.251  dev-kube001.ncl.nhnsystem.com dev-kube001.ncl|
|10.113.232.215	 dev-kube002.ncl.nhnsystem.com dev-kube002.ncl|
|10.113.233.143  dev-kube003.ncl.nhnsystem.com dev-kube003.ncl|
|10.113.233.108  dev-kube004.ncl.nhnsystem.com dev-kube004.ncl|

* packages

| rpm |
|-----|
|etcd-2.1.1-2.el7.x86_64|
|flannel-0.2.0-10.el7.x86_64|
|kubernetes-1.0.3-0.2.gitb9a88a7.el7.x86_64|
|kubernetes-client-1.0.3-0.2.gitb9a88a7.el7.x86_64|
|kubernetes-master-1.0.3-0.2.gitb9a88a7.el7.x86_64|
|kubernetes-node-1.0.3-0.2.gitb9a88a7.el7.x86_64|

### etcd cluster

* reference document

Clustering Guide
> https://coreos.com/etcd/docs/latest/clustering.html

* public etcd discovery

```
[irteamsu@dev-kube001.ncl ~]$ curl https://discovery.etcd.io/new?size=4
https://discovery.etcd.io/0128c2d484d36402abafb011e91284ce
```

* start etcd

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

### kubernetes cluster

* reference document

Kubernetes multiple nodes cluster with flannel on Fedora
> http://kubernetes.io/v1.1/docs/getting-started-guides/fedora/flannel_multi_node_cluster.html

* master setup
