## NODES

### HOW ADD NEW NODES

Steps:

* Create a new group named `new_nodes` and populate it with the new server name and put its vars

```
[node:children]
new_nodes
...
...
[new_nodes]
lb343.enciso.site  ipv4addr=10.64.13.220  k8s_node_group_name=compute  docker_lvm_setup=true  max_pods_per_node=220
```

* Run the playbook

```
sudo ansible-playbook site-scaleup.yml -i inventory-lab --extra-vars "@vars_prerequisites.yml" \
-e "deploy_docker_lvm_storage=true" \
-e "deploy_workers=true" \
-e "deploy_calico=true"
```


> That playbook is idempotent, you could repeat this process any times
