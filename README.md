# Etcd - distributed key-value store

### Prerequisites

- Docker-CE 19.03+
- Docker Compose v1.27+


### Usage

    $ docker-compose pull
    [+] Running 3/3
     ⠿ etcd-3 Pulled                                                       3.9s
     ⠿ etcd-1 Pulled                                                       3.9s
     ⠿ etcd-2 Pulled                                                       3.9s

    $ docker-compose up -d
    [+] Running 4/4
     ⠿ Network etcd-cluster_default     Created                            0.0s
     ⠿ Container etcd-cluster-etcd-3-1  Started                            0.6s
     ⠿ Container etcd-cluster-etcd-1-1  Started                            0.8s
     ⠿ Container etcd-cluster-etcd-2-1  Started                            0.7s

    $ docker exec -it etcd-cluster-etcd-1-1 etcdctl endpoint health
    127.0.0.1:2379 is healthy: successfully committed proposal: took = 2.560575ms

    $ docker exec -it etcd-cluster-etcd-2-1 etcdctl endpoint health
    127.0.0.1:2379 is healthy: successfully committed proposal: took = 2.622971ms

    $ docker exec -it etcd-cluster-etcd-3-1 etcdctl endpoint health
    127.0.0.1:2379 is healthy: successfully committed proposal: took = 2.561252ms

    # put secret from any one of the etcd container
    $ docker exec -it etcd-cluster-etcd-1-1 etcdctl put secret password
    OK

    $ docker exec -it etcd-cluster-etcd-1-1 etcdctl get secret
    secret
    password

    $ docker exec -it etcd-cluster-etcd-2-1 etcdctl get secret
    secret
    password

    $ docker exec -it etcd-cluster-etcd-3-1 etcdctl get secret
    secret
    password

### Docker Images

- [etcd v3.4.18][docker-image-etcd]

[docker-image-etcd]: https://quay.io/repository/coreos/etcd?tab=tags
