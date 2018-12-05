# ipfs-cluster

> it describes IPFS cluster configuration

Private IPFS cluster can be used for backup. That cluster will be composed with one leader node and following nodes.

## Prerequisite

Both leader node and following nodes should initialize environment first.
```bash
# ipfs init
# ipfs-cluster-service init
# ipfs-cluster-ctl init
```

## Run
- Leader node
  1. Run ipfs daemons
  ```bash
  # ipfs daemon
  # ipfs-cluster-service daemon
  ```

- Other nodes
  1. change cluster.secret in ~/.ipfs-cluster/service.json to the secret got 2. of leader node
  2. Run ipfs daemons and connect to leader node
  ```bash
  # ipfs daemon
  # ipfs-cluster-service daemon --bootstrap /ip4/[leader_ip]‌‌‌‌‌‌‌‌/tcp/9096/ipfs/[leader_cluster_id]
  # ipfs swarm connect /ip4/[leader_ip]‌‌‌‌‌‌‌‌/tcp/4001/ipfs/[leader_ipfs_id]
  ```
