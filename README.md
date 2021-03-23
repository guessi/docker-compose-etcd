# Etcd - distributed key-value store

### Prerequisites

- Docker-CE 19.03+
- Docker Compose v1.27+


### Usage

    $ docker-compose up -d

    $ docker exec -it etcd1 etcdctl endpoint health

    $ docker exec -it etcd1 etcdctl put secret password

    $ docker exec -it etcd1 etcdctl get secret


### Docker Images

- [etcd v3.4.15][docker-image-etcd]

[docker-image-etcd]: https://quay.io/repository/coreos/etcd?tab=tags
