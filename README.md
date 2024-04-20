# Etcd - distributed key-value store

### Prerequisites

- Docker 25.0+

### Usage

    $ docker compose pull
    [+] Running 3/3
     ⠿ etcd-3 Pulled                                                       3.9s
     ⠿ etcd-1 Pulled                                                       3.9s
     ⠿ etcd-2 Pulled                                                       3.9s

    $ docker compose up -d
    [+] Running 7/7
     ⠿ Network etcd-cluster_default     Created                            0.1s
     ⠿ Volume "etcd-cluster_etcd3"      Created                            0.0s
     ⠿ Volume "etcd-cluster_etcd1"      Created                            0.0s
     ⠿ Volume "etcd-cluster_etcd2"      Created                            0.0s
     ⠿ Container etcd-cluster-etcd-2-1  Started                            0.9s
     ⠿ Container etcd-cluster-etcd-3-1  Started                            1.1s
     ⠿ Container etcd-cluster-etcd-1-1  Started                            1.1s

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

### Container Images

- [etcd][etcd-repository]

[etcd-repository]: https://quay.io/repository/coreos/etcd?tab=tags
