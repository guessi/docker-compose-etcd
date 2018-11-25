# Etcd - distributed key-value store

### Prerequisites

- Docker-CE 18.06+
- Docker Compose v1.23.1+


### Usage

    $ docker-compose up -d

    $ docker exec -it etcd1 etcdctl set secret password

    $ docker exec -it etcd1 etcdctl get /secret


### Docker Images

- [etcd v3.1.x][docker-image-etcd]

[docker-image-etcd]: https://quay.io/repository/coreos/etcd
