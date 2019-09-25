## ISTIO

Istio will be installed by default, but if you prefer install it manually, run this playbook

```sh
sudo ansible-playbook site.yml -i inventory-lab --extra-vars "@vars_cluster-deploy.yml" -t istio -e "deploy_istio=true"
```

