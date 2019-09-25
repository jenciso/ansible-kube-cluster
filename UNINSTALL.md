## UNINSTALL

Steps:

	sudo ansible -m shell -a "systemctl stop kube-apiserver kube-controller-manager kube-scheduler" -i inventory-lab master
	sudo ansible -m shell -a "systemctl stop etcd" -i inventory-lab etcd
        sudo ansible -m shell -a "systemctl stop kubelet kube-proxy docker" -i inventory-lab node

	sudo ansible -m shell -a 'rm -rf /var/lib/etcd/*' -i inventory-lab etcd
        sudo ansible -m shell -a 'rm -rf /opt/kubernetes' -i inventory-lab master
	sudo ansible -m shell -a 'rm -rf /var/lib/kubernetes /var/lib/kubelet /var/lib/kube-proxy' -i inventory-lab node
