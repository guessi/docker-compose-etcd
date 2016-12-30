# Etcd - distributed key-value store

### Prerequisites

- Docker v1.12.6 (or newer)
- Docker Compose v1.11.2 (or newer)


### Usage

    $ docker-compose up

    $ docker exec -it dockercomposeetcd_etcd-1_1 etcdctl set secret password

    $ docker exec -it dockercomposeetcd_etcd-1_1 etcdctl ls

    $ docker exec -it dockercomposeetcd_etcd-1_1 etcdctl get /secret


### Docker Images

- [etcd v3.1.3][docker-image-etcd]

[docker-image-etcd]: https://quay.io/repository/coreos/etcd
