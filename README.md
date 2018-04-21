# Etcd - distributed key-value store

### Prerequisites

- Docker-CE 17.12+
- Docker Compose v1.21.0+


### Usage

    $ docker-compose up

    $ docker exec -it dockercomposeetcd_etcd-1_1 etcdctl set secret password

    $ docker exec -it dockercomposeetcd_etcd-1_1 etcdctl ls

    $ docker exec -it dockercomposeetcd_etcd-1_1 etcdctl get /secret


### Docker Images

- [etcd v3.1.x][docker-image-etcd]

[docker-image-etcd]: https://quay.io/repository/coreos/etcd
