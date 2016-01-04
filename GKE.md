## GKE

### VM instances
```
gke-cluster-1-7157aa8f-node-cdgm    104.155.239.163     10.240.0.5
gke-cluster-1-7157aa8f-node-e8pz    107.167.184.179     10.240.0.2
gke-cluster-1-7157aa8f-node-l38a    104.155.209.96      10.240.0.6
gke-cluster-1-7157aa8f-node-o0df    107.167.185.223     10.240.0.4
gke-cluster-1-7157aa8f-node-pn3k    130.211.245.31      10.240.0.3
```
---

### cluster1-node1

```
$ gcloud compute ssh gke-cluster-1-7157aa8f-node-cdgm
Warning: Permanently added '104.155.239.163' (ECDSA) to the list of known hosts.
```

#### uname
```
Linux gke-cluster-1-7157aa8f-node-cdgm 3.16.0-0.bpo.4-amd64 #1 SMP Debian 3.16.7-ckt11-1+deb8u4~bpo70+1 (2015-09-22) x86_64

=== GCE Kubernetes node setup complete ===

Last login: Sat Jan  2 22:52:11 2016 from 112.170.92.104

iamyaw@gke-cluster-1-7157aa8f-node-cdgm:~$ uname -a
Linux gke-cluster-1-7157aa8f-node-cdgm 3.16.0-0.bpo.4-amd64 #1 SMP Debian 3.16.7-ckt11-1+deb8u4~bpo70+1 (2015-09-22) x86_64 GNU/Linux
```

#### ps
```
iamyaw@gke-cluster-1-7157aa8f-node-cdgm:~$ ps -ef
UID        PID  PPID  C STIME TTY          TIME CMD
root         1     0  0 22:29 ?        00:00:01 init [2]
root         2     0  0 22:29 ?        00:00:00 [kthreadd]
root         3     2  0 22:29 ?        00:00:03 [ksoftirqd/0]
root         5     2  0 22:29 ?        00:00:00 [kworker/0:0H]
root         7     2  0 22:29 ?        00:00:12 [rcu_sched]
root         8     2  0 22:29 ?        00:00:00 [rcu_bh]
root         9     2  0 22:29 ?        00:00:00 [migration/0]
root        10     2  0 22:29 ?        00:00:04 [watchdog/0]
root        11     2  0 22:29 ?        00:00:00 [khelper]
root        12     2  0 22:29 ?        00:00:00 [kdevtmpfs]
root        13     2  0 22:29 ?        00:00:00 [netns]
root        14     2  0 22:29 ?        00:00:00 [khungtaskd]
root        15     2  0 22:29 ?        00:00:00 [writeback]
root        16     2  0 22:29 ?        00:00:00 [ksmd]
root        17     2  0 22:29 ?        00:00:00 [khugepaged]
root        18     2  0 22:29 ?        00:00:00 [crypto]
root        19     2  0 22:29 ?        00:00:00 [kintegrityd]
root        20     2  0 22:29 ?        00:00:00 [bioset]
root        21     2  0 22:29 ?        00:00:00 [kblockd]
root        22     2  0 22:29 ?        00:00:04 [kworker/0:1]
root        23     2  0 22:29 ?        00:00:06 [kswapd0]
root        24     2  0 22:29 ?        00:00:00 [fsnotify_mark]
root        30     2  0 22:29 ?        00:00:00 [kthrotld]
root        31     2  0 22:29 ?        00:00:00 [ipv6_addrconf]
root        33     2  0 22:29 ?        00:00:00 [deferwq]
root        34     2  0 22:29 ?        00:00:03 [kworker/u2:1]
root       127     2  0 22:29 ?        00:00:00 [scsi_eh_0]
root       128     2  0 22:29 ?        00:00:00 [scsi_tmf_0]
root       129     2  0 22:29 ?        00:00:00 [kworker/u2:2]
root       140     2  0 22:29 ?        00:00:00 [kworker/0:1H]
root       204     2  0 22:29 ?        00:00:00 [jbd2/sda1-8]
root       205     2  0 22:29 ?        00:00:00 [ext4-rsv-conver]
root       351     1  0 22:29 ?        00:00:00 udevd --daemon
root       484     2  0 22:29 ?        00:00:00 [kpsmoused]
root       487     2  0 22:29 ?        00:00:00 [kworker/0:3]
root      1680     1  0 22:29 ?        00:00:00 dhclient -v -pf /run/dhclient.eth0.pid -
root      1761     1  0 22:29 ?        00:00:00 /sbin/rpcbind -w
statd     1792     1  0 22:29 ?        00:00:00 /sbin/rpc.statd
root      1797     2  0 22:29 ?        00:00:00 [rpciod]
root      1799     2  0 22:29 ?        00:00:00 [nfsiod]
root      1806     1  0 22:29 ?        00:00:00 /usr/sbin/rpc.idmapd
root      1880     2  0 22:29 ?        00:00:00 [iscsi_eh]
root      1882     2  0 22:29 ?        00:00:00 [ib_addr]
root      1883     2  0 22:29 ?        00:00:00 [ib_mcast]
root      1884     2  0 22:29 ?        00:00:00 [ib_cm]
root      1885     2  0 22:29 ?        00:00:00 [iw_cm_wq]
root      1886     2  0 22:29 ?        00:00:00 [rdma_cm]
root      1888     1  0 22:29 ?        00:00:01 /usr/sbin/iscsid
root      1889     1  0 22:29 ?        00:00:03 /usr/sbin/iscsid
root      2093     1  0 22:29 ?        00:00:01 /usr/sbin/rsyslogd -c5
root      2125     1  0 22:29 ?        00:00:00 /usr/sbin/acpid
root      2191     1  0 22:29 ?        00:00:00 /usr/sbin/cron
root      2478     1  0 22:29 ?        00:00:00 /usr/sbin/sshd
root      2545     1  0 22:29 ?        00:00:00 startpar -f -- google-accounts-manager
root      2548     1  0 22:29 ?        00:00:00 /usr/bin/python /usr/share/google/google
root      2560     1  0 22:29 ?        00:00:00 /usr/bin/python /usr/share/google/google
root      2572     1  0 22:29 ?        00:00:00 /usr/bin/python /usr/share/google/google
ntp       2596     1  0 22:29 ?        00:00:05 /usr/sbin/ntpd -p /var/run/ntpd.pid -g -
root      3211     1  0 22:30 ?        00:00:00 /usr/bin/python /usr/bin/supervisord -c
root      3215     1  0 22:30 tty1     00:00:00 /sbin/getty 38400 tty1
root      3216     1  0 22:30 tty2     00:00:00 /sbin/getty 38400 tty2
root      3217     1  0 22:30 tty3     00:00:00 /sbin/getty 38400 tty3
root      3218     1  0 22:30 tty4     00:00:00 /sbin/getty 38400 tty4
root      3219     1  0 22:30 tty5     00:00:00 /sbin/getty 38400 tty5
root      3220     1  0 22:30 tty6     00:00:00 /sbin/getty 38400 tty6
root      3221  3211  0 22:30 ?        00:00:00 /bin/bash /usr/sbin/kubelet-checker.sh
root      3222  3211  0 22:30 ?        00:00:00 /bin/bash /usr/sbin/kube-proxy-checker.s
root      3223  3211  0 22:30 ?        00:00:00 /bin/bash /usr/sbin/docker-checker.sh
root      3272     1  3 22:30 ?        00:01:06 /usr/local/bin/kubelet --api-servers=htt
root      3273     1  0 22:30 ?        00:00:05 /usr/local/bin/kube-proxy --master=https
root      3509     1  4 22:31 ?        00:01:21 /usr/bin/docker -d -p /var/run/docker.pi
root      3539   351  0 22:31 ?        00:00:00 udevd --daemon
root      3561  3509  0 22:31 ?        00:00:00 /pause
root      3595   351  0 22:31 ?        00:00:00 udevd --daemon
root      3616  3509  0 22:31 ?        00:00:00 /pause
root      4178  3509  0 22:34 ?        00:00:00 /bin/sh -c /usr/sbin/google-fluentd "$FL
root      4187  4178  0 22:34 ?        00:00:05 /opt/google-fluentd/embedded/bin/ruby /u
root      4207  4187  3 22:34 ?        00:00:44 /opt/google-fluentd/embedded/bin/ruby /u
root      4237  3509  0 22:34 ?        00:00:06 /usr/local/bin/etcd -data-dir /var/etcd/
root      4356  3509  0 22:34 ?        00:00:00 /kube2sky -domain=cluster.local
root      4553  3509  1 22:35 ?        00:00:22 /skydns -machines=http://127.0.0.1:4001
root      4630  3509  0 22:35 ?        00:00:00 /exechealthz -cmd=nslookup kubernetes.de
root      9399  2478  0 22:55 ?        00:00:00 sshd: gke-7157aa8f566585af37e7 [priv]
1000      9401  9399  0 22:55 ?        00:00:00 sshd: gke-7157aa8f566585af37e7
root      9521  2478  0 22:56 ?        00:00:00 sshd: iamyaw [priv]
iamyaw    9523  9521  0 22:56 ?        00:00:00 sshd: iamyaw@pts/0
iamyaw    9524  9523  0 22:56 pts/0    00:00:00 -bash
root     10010  2548  0 22:58 ?        00:00:00 /usr/bin/python /usr/share/google/google
root     10078  3221  0 22:58 ?        00:00:00 sleep 10
root     10082  3222  0 22:58 ?        00:00:00 sleep 10
root     10091  3223  0 22:58 ?        00:00:00 sleep 10
iamyaw   10095  9524  0 22:58 pts/0    00:00:00 ps -ef
```

#### docker ps
```
iamyaw@gke-cluster-1-7157aa8f-node-cdgm:~$ sudo docker ps -a
CONTAINER ID        IMAGE                                                COMMAND                  CREATED             STATUS              PORTS               NAMES
c718785bca47        gcr.io/google_containers/exechealthz:1.0             "/exechealthz '-cmd=n"   About an hour ago   Up About an hour                        k8s_healthz.fab416b0_kube-dns-v9-nq173_kube-system_7f3aa873-b1a0-11e5-b20d-42010af000de_d1565be3
a26d039d3e37        gcr.io/google_containers/skydns:2015-10-13-8c72f8c   "/skydns -machines=ht"   About an hour ago   Up About an hour                        k8s_skydns.b6d2145c_kube-dns-v9-nq173_kube-system_7f3aa873-b1a0-11e5-b20d-42010af000de_cbf64de9
cb25c10458de        gcr.io/google_containers/kube2sky:1.11               "/kube2sky -domain=cl"   About an hour ago   Up About an hour                        k8s_kube2sky.529ede94_kube-dns-v9-nq173_kube-system_7f3aa873-b1a0-11e5-b20d-42010af000de_a8f190b4
c5e4a30bd651        gcr.io/google_containers/etcd:2.0.9                  "/usr/local/bin/etcd "   About an hour ago   Up About an hour                        k8s_etcd.ee82335b_kube-dns-v9-nq173_kube-system_7f3aa873-b1a0-11e5-b20d-42010af000de_09458d2b
97fc7ecf3c41        gcr.io/google_containers/fluentd-gcp:1.14            "/bin/sh -c '/usr/sbi"   About an hour ago   Up About an hour                        k8s_fluentd-cloud-logging.d2410c63_fluentd-cloud-logging-gke-cluster-1-7157aa8f-node-cdgm_kube-system_632e2edb4c1261f8db2169ec87ee822a_d6df93f1
ca5a35e07864        gcr.io/google_containers/pause:0.8.0                 "/pause"                 About an hour ago   Up About an hour                        k8s_POD.63f848fb_kube-dns-v9-nq173_kube-system_7f3aa873-b1a0-11e5-b20d-42010af000de_d9b69021
14183068ea9a        gcr.io/google_containers/pause:0.8.0                 "/pause"                 About an hour ago   Up About an hour                        k8s_POD.6d00e006_fluentd-cloud-logging-gke-cluster-1-7157aa8f-node-cdgm_kube-system_632e2edb4c1261f8db2169ec87ee822a_b661f3ee
```

#### docker images
```
iamyaw@gke-cluster-1-7157aa8f-node-cdgm:~$ sudo docker images
REPOSITORY                             TAG                  IMAGE ID            CREATED             VIRTUAL SIZE
gcr.io/google_containers/fluentd-gcp   1.14                 7303eb586228        9 weeks ago         410.1 MB
gcr.io/google_containers/skydns        2015-10-13-8c72f8c   763c92e53f31        11 weeks ago        40.55 MB
gcr.io/google_containers/exechealthz   1.0                  4f3d04b1d47b        5 months ago        7.099 MB
gcr.io/google_containers/kube2sky      1.11                 e52a547dca17        6 months ago        19.17 MB
gcr.io/google_containers/etcd          2.0.9                b6b9a86dc06a        9 months ago        12.82 MB
gcr.io/google_containers/pause         0.8.0                2c40b0526b63        9 months ago        241.7 kB
```

#### etcd command arg
```
iamyaw@gke-cluster-1-7157aa8f-node-cdgm:~$ ps -ef | grep etcd
root      4237  3509  0 22:34 ?        00:00:19 /usr/local/bin/etcd -data-dir /var/etcd/data -listen-client-urls http://127.0.0.1:2379,http://127.0.0.1:4001 -advertise-client-urls http://127.0.0.1:2379,http://127.0.0.1:4001 -initial-cluster-token skydns-etcd
```

#### kubernetes ps
```
iamyaw@gke-cluster-1-7157aa8f-node-cdgm:~$ ps -ef | grep kube
root      3221  3211  0 22:30 ?        00:00:00 /bin/bash /usr/sbin/kubelet-checker.sh
root      3222  3211  0 22:30 ?        00:00:00 /bin/bash /usr/sbin/kube-proxy-checker.sh
root      3272     1  2 22:30 ?        00:02:13 /usr/local/bin/kubelet --api-servers=https://104.199.138.89 --enable-debugging-handlers=true --cloud-provider=gce --config=/etc/kubernetes/manifests --allow-privileged=True --v=2 --cluster-dns=10.123.240.10 --cluster-domain=cluster.local --configure-cbr0=true --cgroup-root=/ --system-container=/system
root      3273     1  0 22:30 ?        00:00:13 /usr/local/bin/kube-proxy --master=https://104.199.138.89 --kubeconfig=/var/lib/kube-proxy/kubeconfig --v=2
root      4356  3509  0 22:34 ?        00:00:00 /kube2sky -domain=cluster.local
root      4630  3509  0 22:35 ?        00:00:01 /exechealthz -cmd=nslookup kubernetes.default.svc.cluster.local localhost >/dev/null -port=8080
iamyaw   22353 20251  0 23:51 pts/2    00:00:00 grep kube
```

#### shell script
```
iamyaw@gke-cluster-1-7157aa8f-node-cdgm:~$ ps -ef | grep '\.sh'
root      3221  3211  0 22:30 ?        00:00:00 /bin/bash /usr/sbin/kubelet-checker.sh
root      3222  3211  0 22:30 ?        00:00:00 /bin/bash /usr/sbin/kube-proxy-checker.sh
root      3223  3211  0 22:30 ?        00:00:00 /bin/bash /usr/sbin/docker-checker.sh
iamyaw   23688 20251  0 23:57 pts/2    00:00:00 grep \.sh
```

#### python script
```
amyaw@gke-cluster-1-7157aa8f-node-cdgm:~$ ps -ef | grep python
root      2548     1  0 22:29 ?        00:00:00 /usr/bin/python /usr/share/google/google_daemon/manage_accounts.py --daemon
root      2560     1  0 22:29 ?        00:00:00 /usr/bin/python /usr/share/google/google_daemon/manage_addresses.py
root      2572     1  0 22:29 ?        00:00:00 /usr/bin/python /usr/share/google/google_daemon/manage_clock_sync.py
root      3211     1  0 22:30 ?        00:00:01 /usr/bin/python /usr/bin/supervisord -c /etc/supervisor/supervisord.conf
root     24272  2548  0 23:59 ?        00:00:00 /usr/bin/python /usr/share/google/google_daemon/manage_accounts.py --daemon
iamyaw   24338 20251  0 23:59 pts/2    00:00:00 grep python
```

#### ip addr
```
iamyaw@gke-cluster-1-7157aa8f-node-cdgm:~$ ip addr
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1460 qdisc pfifo_fast state UP qlen 1000
    link/ether 42:01:0a:f0:00:05 brd ff:ff:ff:ff:ff:ff
    inet 10.240.0.5/32 brd 10.240.0.5 scope global eth0
       valid_lft forever preferred_lft forever
4: cbr0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1460 qdisc htb state UP
    link/ether ae:3b:7b:cc:f6:a6 brd ff:ff:ff:ff:ff:ff
    inet 10.120.4.1/24 scope global cbr0
       valid_lft forever preferred_lft forever
10: vethc3e81bf: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1460 qdisc noqueue master cbr0 state UP
    link/ether ae:3b:7b:cc:f6:a6 brd ff:ff:ff:ff:ff:ff
12: vethb4c31b6: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1460 qdisc noqueue master cbr0 state UP
    link/ether de:c4:1f:57:ac:da brd ff:ff:ff:ff:ff:ff
```

#### ip route
```
iamyaw@gke-cluster-1-7157aa8f-node-cdgm:~$ ip route
default via 10.240.0.1 dev eth0
10.120.4.0/24 dev cbr0  proto kernel  scope link  src 10.120.4.1
10.240.0.1 dev eth0  scope link
```
---

### cluster1-node2

#### docker ps
```
iamyaw@gke-cluster-1-7157aa8f-node-e8p6:~$ sudo docker ps -a
CONTAINER ID        IMAGE                                         COMMAND                  CREATED             STATUS              PORTS               NAMES
4f5a1e3dab7e        gcr.io/google_containers/defaultbackend:1.0   "/server"                About an hour ago   Up About an hour                        k8s_default-http-backend.e2ec6c5f_l7-lb-controller-iudmz_kube-system_7f3a4447-b1a0-11e5-b20d-42010af000de_c61c2bbe
f4768ded0a45        gcr.io/google_containers/glbc:0.5.1           "/glbc --default-back"   About an hour ago   Up About an hour                        k8s_l7-lb-controller.b3da613c_l7-lb-controller-iudmz_kube-system_7f3a4447-b1a0-11e5-b20d-42010af000de_505f926f
87238de501fe        gcr.io/google_containers/fluentd-gcp:1.14     "/bin/sh -c '/usr/sbi"   About an hour ago   Up About an hour                        k8s_fluentd-cloud-logging.d2410c63_fluentd-cloud-logging-gke-cluster-1-7157aa8f-node-e8p6_kube-system_632e2edb4c1261f8db2169ec87ee822a_d3f0cd4f
91ab494631c4        gcr.io/google_containers/pause:0.8.0          "/pause"                 About an hour ago   Up About an hour                        k8s_POD.68110139_l7-lb-controller-iudmz_kube-system_7f3a4447-b1a0-11e5-b20d-42010af000de_b8cd3609
5bc79aaa1573        gcr.io/google_containers/pause:0.8.0          "/pause"                 About an hour ago   Up About an hour                        k8s_POD.6d00e006_fluentd-cloud-logging-gke-cluster-1-7157aa8f-node-e8p6_kube-system_632e2edb4c1261f8db2169ec87ee822a_8ba11cd9
```

#### docker images
```
iamyaw@gke-cluster-1-7157aa8f-node-e8p6:~$ sudo docker images
REPOSITORY                                TAG                 IMAGE ID            CREATED             VIRTUAL SIZE
gcr.io/google_containers/glbc             0.5.1               3a20dde654dc        5 weeks ago         224.8 MB
gcr.io/google_containers/fluentd-gcp      1.14                7303eb586228        9 weeks ago         410.1 MB
gcr.io/google_containers/defaultbackend   1.0                 7f244066fca1        10 weeks ago        7.514 MB
gcr.io/google_containers/pause            0.8.0               2c40b0526b63        9 months ago        241.7 kB
```

#### kubernetes ps
```
iamyaw@gke-cluster-1-7157aa8f-node-e8p6:~$ ps -ef | grep kube
root      3225  3215  0 Jan02 ?        00:00:01 /bin/bash /usr/sbin/kubelet-checker.sh
root      3226  3215  0 Jan02 ?        00:00:01 /bin/bash /usr/sbin/kube-proxy-checker.sh
root      3277     1  1 Jan02 ?        00:10:51 /usr/local/bin/kubelet --api-servers=https://104.199.138.89 --enable-debugging-handlers=true --cloud-provider=gce --config=/etc/kubernetes/manifests --allow-privileged=True --v=2 --cluster-dns=10.123.240.10 --cluster-domain=cluster.local --configure-cbr0=true --cgroup-root=/ --system-container=/system
root      3278     1  0 Jan02 ?        00:01:30 /usr/local/bin/kube-proxy --master=https://104.199.138.89 --kubeconfig=/var/lib/kube-proxy/kubeconfig --v=2
root      4437  3504  0 Jan02 ?        00:00:17 /glbc --default-backend-service=kube-system/default-http-backend --sync-period=300s
iamyaw    7805  7291  0 08:12 pts/1    00:00:00 grep kube
```

#### ip addr eth0
```
iamyaw@gke-cluster-1-7157aa8f-node-e8p6:~$ ip addr show dev eth0
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1460 qdisc pfifo_fast state UP qlen 1000
    link/ether 42:01:0a:f0:00:02 brd ff:ff:ff:ff:ff:ff
    inet 10.240.0.2/32 brd 10.240.0.2 scope global eth0
       valid_lft forever preferred_lft forever
```
---

### cluster1-node3

#### docker ps
```
iamyaw@gke-cluster-1-7157aa8f-node-l38a:~$ sudo docker ps -a
CONTAINER ID        IMAGE                                       COMMAND                  CREATED             STATUS              PORTS               NAMES
5f28173603c4        gcr.io/google_containers/kube-ui:v2         "/kube-ui"               About an hour ago   Up About an hour                        k8s_kube-ui.8a3f618a_kube-ui-v2-z5zva_kube-system_7f39bcfc-b1a0-11e5-b20d-42010af000de_f1b31781
04457b91e5a9        gcr.io/google_containers/fluentd-gcp:1.14   "/bin/sh -c '/usr/sbi"   About an hour ago   Up About an hour                        k8s_fluentd-cloud-logging.d2410c63_fluentd-cloud-logging-gke-cluster-1-7157aa8f-node-l38a_kube-system_632e2edb4c1261f8db2169ec87ee822a_8cd3966c
35c141caa859        gcr.io/google_containers/pause:0.8.0        "/pause"                 About an hour ago   Up About an hour                        k8s_POD.68110139_kube-ui-v2-z5zva_kube-system_7f39bcfc-b1a0-11e5-b20d-42010af000de_7a5fe9c7
348d5956c1af        gcr.io/google_containers/pause:0.8.0        "/pause"                 About an hour ago   Up About an hour                        k8s_POD.6d00e006_fluentd-cloud-logging-gke-cluster-1-7157aa8f-node-l38a_kube-system_632e2edb4c1261f8db2169ec87ee822a_4e4b6a32
```

#### docker images
```
iamyaw@gke-cluster-1-7157aa8f-node-l38a:~$ sudo docker images
REPOSITORY                             TAG                 IMAGE ID            CREATED             VIRTUAL SIZE
gcr.io/google_containers/fluentd-gcp   1.14                7303eb586228        9 weeks ago         410.1 MB
gcr.io/google_containers/kube-ui       v2                  6286e698abf4        4 months ago        5.673 MB
gcr.io/google_containers/pause         0.8.0               2c40b0526b63        9 months ago        241.7 kB
```

#### kubernetes ps
```
iamyaw@gke-cluster-1-7157aa8f-node-l38a:~$ ps -ef | grep kube
root      3223  3213  0 Jan02 ?        00:00:01 /bin/bash /usr/sbin/kubelet-checker.sh
root      3224  3213  0 Jan02 ?        00:00:01 /bin/bash /usr/sbin/kube-proxy-checker.sh
root      3273     1  0 Jan02 ?        00:01:26 /usr/local/bin/kube-proxy --master=https://104.199.138.89 --kubeconfig=/var/lib/kube-proxy/kubeconfig --v=2
root      3275     1  1 Jan02 ?        00:09:31 /usr/local/bin/kubelet --api-servers=https://104.199.138.89 --enable-debugging-handlers=true --cloud-provider=gce --config=/etc/kubernetes/manifests --allow-privileged=True --v=2 --cluster-dns=10.123.240.10 --cluster-domain=cluster.local --configure-cbr0=true --cgroup-root=/ --system-container=/system
root      4203  3508  0 Jan02 ?        00:00:02 /kube-ui
iamyaw    7270  6823  0 08:12 pts/0    00:00:00 grep kube
```

#### ip addr eth0
```
iamyaw@gke-cluster-1-7157aa8f-node-l38a:~$ ip addr show dev eth0
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1460 qdisc pfifo_fast state UP qlen 1000
    link/ether 42:01:0a:f0:00:06 brd ff:ff:ff:ff:ff:ff
    inet 10.240.0.6/32 brd 10.240.0.6 scope global eth0
       valid_lft forever preferred_lft forever
```
---

### cluster1-node4

#### docker ps
```
iamyaw@gke-cluster-1-7157aa8f-node-o0df:~$ sudo docker ps -a
CONTAINER ID        IMAGE                                       COMMAND                  CREATED             STATUS              PORTS               NAMES
0cab9c1bea9b        gcr.io/google_containers/heapster:v0.18.2   "/heapster --source=k"   9 hours ago         Up 9 hours                              k8s_heapster.fdae40a_heapster-v10-jcblx_kube-system_7f3a4fa8-b1a0-11e5-b20d-42010af000de_53a9d358
62d35b57c813        gcr.io/google_containers/fluentd-gcp:1.14   "/bin/sh -c '/usr/sbi"   9 hours ago         Up 9 hours                              k8s_fluentd-cloud-logging.d2410c63_fluentd-cloud-logging-gke-cluster-1-7157aa8f-node-o0df_kube-system_632e2edb4c1261f8db2169ec87ee822a_16a93266
df3a6dcdaf72        gcr.io/google_containers/pause:0.8.0        "/pause"                 9 hours ago         Up 9 hours                              k8s_POD.6d00e006_heapster-v10-jcblx_kube-system_7f3a4fa8-b1a0-11e5-b20d-42010af000de_fbc374bc
cb59351d3bd0        gcr.io/google_containers/pause:0.8.0        "/pause"                 9 hours ago         Up 9 hours                              k8s_POD.6d00e006_fluentd-cloud-logging-gke-cluster-1-7157aa8f-node-o0df_kube-system_632e2edb4c1261f8db2169ec87ee822a_27da9f92
```

#### docker images
```
iamyaw@gke-cluster-1-7157aa8f-node-o0df:~$ sudo docker images
REPOSITORY                             TAG                 IMAGE ID            CREATED             VIRTUAL SIZE
gcr.io/google_containers/fluentd-gcp   1.14                7303eb586228        9 weeks ago         410.1 MB
gcr.io/google_containers/heapster      v0.18.2             899df50acd84        3 months ago        34.52 MB
gcr.io/google_containers/pause         0.8.0               2c40b0526b63        9 months ago        241.7 kB
```

#### kubernetes ps
```
iamyaw@gke-cluster-1-7157aa8f-node-o0df:~$ ps -ef | grep kube
root      3228  3218  0 Jan02 ?        00:00:01 /bin/bash /usr/sbin/kubelet-checker.sh
root      3229  3218  0 Jan02 ?        00:00:01 /bin/bash /usr/sbin/kube-proxy-checker.sh
root      3278     1  0 Jan02 ?        00:01:27 /usr/local/bin/kube-proxy --master=https://104.199.138.89 --kubeconfig=/var/lib/kube-proxy/kubeconfig --v=2
root      3280     1  1 Jan02 ?        00:09:57 /usr/local/bin/kubelet --api-servers=https://104.199.138.89 --enable-debugging-handlers=true --cloud-provider=gce --config=/etc/kubernetes/manifests --allow-privileged=True --v=2 --cluster-dns=10.123.240.10 --cluster-domain=cluster.local --configure-cbr0=true --cgroup-root=/ --system-container=/system
root      4265  3510  1 Jan02 ?        00:06:27 /heapster --source=kubernetes:''
iamyaw    7437  6986  0 08:12 pts/1    00:00:00 grep kube
```

#### ip addr eth0
```
iamyaw@gke-cluster-1-7157aa8f-node-o0df:~$ ip addr show dev eth0
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1460 qdisc pfifo_fast state UP qlen 1000
    link/ether 42:01:0a:f0:00:04 brd ff:ff:ff:ff:ff:ff
    inet 10.240.0.4/32 brd 10.240.0.4 scope global eth0
       valid_lft forever preferred_lft forever
```
---

### cluster1-node5

#### docker ps
```
amyaw@gke-cluster-1-7157aa8f-node-pn3k:~$ sudo docker ps -a
CONTAINER ID        IMAGE                                       COMMAND                  CREATED             STATUS              PORTS               NAMES
e52188f7d32d        gcr.io/google_containers/fluentd-gcp:1.14   "/bin/sh -c '/usr/sbi"   9 hours ago         Up 9 hours                              k8s_fluentd-cloud-logging.d2410c63_fluentd-cloud-logging-gke-cluster-1-7157aa8f-node-pn3k_kube-system_632e2edb4c1261f8db2169ec87ee822a_12dcdb55
0babb795404d        gcr.io/google_containers/pause:0.8.0        "/pause"                 9 hours ago         Up 9 hours                              k8s_POD.6d00e006_fluentd-cloud-logging-gke-cluster-1-7157aa8f-node-pn3k_kube-system_632e2edb4c1261f8db2169ec87ee822a_38096b39
```

#### docker images
```
iamyaw@gke-cluster-1-7157aa8f-node-pn3k:~$ sudo docker images
REPOSITORY                             TAG                 IMAGE ID            CREATED             VIRTUAL SIZE
gcr.io/google_containers/fluentd-gcp   1.14                7303eb586228        9 weeks ago         410.1 MB
gcr.io/google_containers/pause         0.8.0               2c40b0526b63        9 months ago        241.7 kB
```

#### kubernetes ps
```
iamyaw@gke-cluster-1-7157aa8f-node-pn3k:~$ ps -ef | grep kube
root      3170  3160  0 Jan02 ?        00:00:01 /bin/bash /usr/sbin/kubelet-checker.sh
root      3171  3160  0 Jan02 ?        00:00:01 /bin/bash /usr/sbin/kube-proxy-checker.sh
root      3220     1  0 Jan02 ?        00:01:21 /usr/local/bin/kube-proxy --master=https://104.199.138.89 --kubeconfig=/var/lib/kube-proxy/kubeconfig --v=2
root      3222     1  1 Jan02 ?        00:08:29 /usr/local/bin/kubelet --api-servers=https://104.199.138.89 --enable-debugging-handlers=true --cloud-provider=gce --config=/etc/kubernetes/manifests --allow-privileged=True --v=2 --cluster-dns=10.123.240.10 --cluster-domain=cluster.local --configure-cbr0=true --cgroup-root=/ --system-container=/system
iamyaw    5851  5453  0 08:12 pts/0    00:00:00 grep kube
```

#### ip addr eth0
```
iamyaw@gke-cluster-1-7157aa8f-node-pn3k:~$ ip addr show dev eth0
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1460 qdisc pfifo_fast state UP qlen 1000
    link/ether 42:01:0a:f0:00:03 brd ff:ff:ff:ff:ff:ff
    inet 10.240.0.3/32 brd 10.240.0.3 scope global eth0
       valid_lft forever preferred_lft forever
```
---

### cluster-master

#### kubernetes nodes services namespaces components endpoints
```
iamyaw@iamyaw-cloud:~$ kubectl get nodes
NAME                               LABELS                                                    STATUS    AGE
gke-cluster-1-7157aa8f-node-cdgm   kubernetes.io/hostname=gke-cluster-1-7157aa8f-node-cdgm   Ready     1d
gke-cluster-1-7157aa8f-node-e8p6   kubernetes.io/hostname=gke-cluster-1-7157aa8f-node-e8p6   Ready     1d
gke-cluster-1-7157aa8f-node-l38a   kubernetes.io/hostname=gke-cluster-1-7157aa8f-node-l38a   Ready     1d
gke-cluster-1-7157aa8f-node-o0df   kubernetes.io/hostname=gke-cluster-1-7157aa8f-node-o0df   Ready     1d
gke-cluster-1-7157aa8f-node-pn3k   kubernetes.io/hostname=gke-cluster-1-7157aa8f-node-pn3k   Ready     1d

iamyaw@iamyaw-cloud:~$ kubectl get svc
NAME         CLUSTER_IP     EXTERNAL_IP   PORT(S)   SELECTOR   AGE
kubernetes   10.123.240.1   <none>        443/TCP   <none>     1d

iamyaw@iamyaw-cloud:~$ kubectl get ns
NAME          LABELS    STATUS    AGE
default       <none>    Active    1d
kube-system   <none>    Active    1d

iamyaw@iamyaw-cloud:~$ kubectl get cs
NAME                 STATUS    MESSAGE              ERROR
scheduler            Healthy   ok                   nil
etcd-0               Healthy   {"health": "true"}   nil
etcd-1               Healthy   {"health": "true"}   nil
controller-manager   Healthy   ok                   nil

iamyaw@iamyaw-cloud:~$ kubectl get ep
NAME         ENDPOINTS            AGE
kubernetes   104.199.138.89:443   1d
```

#### kubernetes service detail
```
iamyaw@iamyaw-cloud:~$ kubectl describe svc
Name:                   kubernetes
Namespace:              default
Labels:                 component=apiserver,provider=kubernetes
Selector:               <none>
Type:                   ClusterIP
IP:                     10.123.240.1
Port:                   <unnamed>       443/TCP
Endpoints:              104.199.138.89:443
Session Affinity:       None
No events.
```

#### kubernetes node detail
```
iamyaw@iamyaw-cloud:~$ kubectl describe nodes
Name:                   gke-cluster-1-7157aa8f-node-cdgm
Labels:                 kubernetes.io/hostname=gke-cluster-1-7157aa8f-node-cdgm
CreationTimestamp:      Sun, 03 Jan 2016 07:30:49 +0900
Phase:
Conditions:
  Type          Status  LastHeartbeatTime                       LastTransitionTime                      Reason                          Message
  ────          ──────  ─────────────────                       ──────────────────                      ──────                          ───────
  OutOfDisk     False   Mon, 04 Jan 2016 16:58:05 +0900         Sun, 03 Jan 2016 07:30:49 +0900         KubeletHasSufficientDisk        kubelet has sufficient disk space available
  Ready         True    Mon, 04 Jan 2016 16:58:05 +0900         Mon, 04 Jan 2016 15:46:56 +0900         KubeletReady                    kubelet is posting ready status
Addresses:      10.240.0.5,104.155.239.163
Capacity:
 pods:          40
 cpu:           1
 memory:        608496Ki
System Info:
 Machine ID:
 System UUID:                   0751FF1F-0A94-678B-2C8A-F56078B7174D
 Boot ID:                       ee793216-5899-4205-afe9-6f9ee9eccc9f
 Kernel Version:                3.16.0-0.bpo.4-amd64
 OS Image:                      Debian GNU/Linux 7 (wheezy)
 Container Runtime Version:     docker://1.8.3
 Kubelet Version:               v1.1.3
 Kube-Proxy Version:            v1.1.3
PodCIDR:                        10.120.4.0/24
ExternalID:                     6217321892169312588
Non-terminated Pods:            (2 in total)
  Namespace                     Name                                                            CPU Requests    CPU Limits      Memory Requests Memory Limits
  ─────────                     ────                                                            ────────────    ──────────      ─────────────── ─────────────
  kube-system                   fluentd-cloud-logging-gke-cluster-1-7157aa8f-node-cdgm          100m (10%)      100m (10%)      200Mi (33%)     200Mi (33%)
  kube-system                   kube-dns-v9-nq173                                               310m (31%)      310m (31%)      170Mi (28%)     170Mi (28%)
Allocated resources:
  (Total limits may be over 100%, i.e., overcommitted. More info: http://releases.k8s.io/HEAD/docs/user-guide/compute-resources.md)
  CPU Requests  CPU Limits      Memory Requests Memory Limits
  ────────────  ──────────      ─────────────── ─────────────
  410m (41%)    410m (41%)      370Mi (62%)     370Mi (62%)
No events.
```

#### kubectl config
```
iamyaw@iamyaw-cloud:~$ kubectl config view
apiVersion: v1
clusters:
- cluster:
    certificate-authority-data: REDACTED
    server: https://104.199.138.89
  name: gke_iamyaw-cloud_asia-east1-a_cluster-1
contexts:
- context:
    cluster: gke_iamyaw-cloud_asia-east1-a_cluster-1
    user: gke_iamyaw-cloud_asia-east1-a_cluster-1
  name: gke_iamyaw-cloud_asia-east1-a_cluster-1
current-context: gke_iamyaw-cloud_asia-east1-a_cluster-1
kind: Config
preferences: {}
users:
- name: gke_iamyaw-cloud_asia-east1-a_cluster-1
  user:
    client-certificate-data: REDACTED
    client-key-data: REDACTED
    password: mq66VGUqH5jDDvOI
    username: admin
```
