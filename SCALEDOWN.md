# SCALEDOWN

## HOW DELETE NODES

Steps:

* Delete the node from the inventory file. For example, it should be into the group `node_compute`, delete this line

```
[node_compute]
dcbvm090lb343.e-unicred.com.br  ipv4addr=10.64.13.220  k8s_node_group_name=compute  docker_lvm_setup=true  max_pods_per_node=220
```

* Drain all the containers into the node

```
kubectl drain dcbvm090lb343.e-unicred.com.br --ignore-daemonsets
```

* Finally, delete the node

```
kubectl delete node dcbvm090lb343.e-unicred.com.br
```

> In the new versions of calico isn't necessary use calicoctl to delete anything. This step will be done automatically
