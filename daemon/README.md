### Run Ceph Mon

```console
#docker run -ti --net=host -e MON_IP=10.1.4.12 -e CEPH_PUBLIC_NETWORK=10.1.4.0/24 -e CEPH_DAEMON=mon cephdaemon/daemon
```
