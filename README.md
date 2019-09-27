# KUBE-CLUSTER

<img src="https://kubernetes.io/images/kubernetes-horizontal-color.png" width="500" align="center">

This playbook is based in the documment [Kubernetes the Hard Way](https://github.com/kelseyhightower/kubernetes-the-hard-way)

<br/>

## Features

- Kubernetes 1.15
- High Availability Cluster
- Master nodes are running etcd daemon in cluster mode
- Automatic node register using bootstrap option
- RBAC Authentication
- Calico Network Support (new version)
- Docker 18.09
- CoreDNS 1.4
- GlusterFS - CNS
- Istio 1.1.7

## Requirements 

* 13 VM's Centos 7
* 1 ansible host (to run this playbook)

Minimal Setup:

| # | Type | CPU's | Memory | Disk |
|:--|:-----|:------|:-------|:-----|
| 2 | LoadBalancer | 1 vCPU | 1 GB  | SO: /dev/sda (30GB), Storage Container: /dev/sdb (50GB) |
| 3 | Etcd         | 4 vCPU | 4 GB  | SO: /dev/sda (30GB), Storage Container: /dev/sdb (50GB) |
| 3 | Master       | 4 vCPU | 8 GB  | SO: /dev/sda (30GB), Storage Container: /dev/sdb (50GB) |
| 3 | Node Infra   | 4 vCPU | 8 GB  | SO: /dev/sda (30GB), Storage Container: /dev/sdb (50GB), Glusterfs: /dev/sdc (150GB) |
| 2 | Node Compute | 4 vCPU | 8 GB  | SO: /dev/sda (30GB), Storage Container: /dev/sdb (50GB) |


## INSTALLATION

### First of all 

Create a domain for your apiserver. Ex. `apik8s-lab.tre-rs.gov.br` and set the var `api_domain` into the `group_vars/all/main.yml` file 

### Install

Follow the instructions from [INSTALL.md](INSTALL.md).
