# INSTALL


* Step 1: Running the pre-requisites playbook

```bash
sudo ansible-playbook site-prerequisites.yml -i inventory-lab --extra-vars "@vars_prerequisites.yml" -e "deploy_docker_lvm_storage=true"
```

* Step 2: Deploying the cluster

```
sudo ansible-playbook site.yml -i inventory-lab --extra-vars "@vars_cluster-deploy.yml"
```

## Notes:

* If you want to upgrade all centos packages, you need to use `-e upgrade_packages=true`. It will take around 30min to upgrade all the packages.
* If you have another partition to mount `/var/lib/docker`, you could to use `deploy_docker_lvm_storage=true`, the default disk is `/dev/sdb`

