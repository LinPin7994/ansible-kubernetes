# ansible-kubernetes
Edit group_vars and hosts.
If you want use crio or containerd, comment kubernetes-docker role in playbook.
Edit vars in vars/main.yaml and if you use kubernetes-crio-containerd role, edit vars in defaults/main.yaml in role.

For one master:
Stay haproxy in hosts empty and delete ip address in master. Leave only init-master host.

For multi-master:
Set ip address in init-master, master and haproxy if it needed.

For add new node in cluster:
1. Commnet exists node in host file.
2. Add new node ip address.
3. run:
 ansible-playbook playbook/kubernetes.yaml --tags="pre_install,requirements,post_install" --limit="new_node_ip"
 ansible-playbook playbook/kubernetes.yaml --tags="gen_vars,join_node,labels_node"

Both roles testing on vagrant centos7 box.
