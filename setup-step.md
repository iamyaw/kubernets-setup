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
|docker-selinux-1.8.2-7.el7.centos.x86_64|
|docker-1.8.2-7.el7.centos.x86_64|

### etcd cluster

* reference document

Clustering Guide
> https://coreos.com/etcd/docs/2.1.0/clustering.html

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

### flannel

* reference document

Configuring flannel for Container Networking
>https://coreos.com/flannel/docs/0.5.0/flannel-config.html

* publishing config to etcd
```
etcdctl set /coreos.com/network/config '{
  "Network": "10.1.0.0/16",
  "SubnetLen": 24
}'
```

### kubernetes cluster

* reference document

Kubernetes multiple nodes cluster with flannel on Fedora
>http://kubernetes.io/v1.0/docs/getting-started-guides/fedora/flannel_multi_node_cluster.html

Running Multi-Node Kubernetes Using Docker
>http://kubernetes.io/v1.0/docs/getting-started-guides/docker-multinode.html

* master setup
