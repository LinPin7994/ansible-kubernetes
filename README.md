# ansible-kubernetes
Edit group_vars and hosts.
If you want use crio or containerd, comment kubernetes-docker role in playbook.
Edit vars in vars/main.yaml and if you use kubernetes-crio-containerd role, edit vars in defaults/main.yaml in role.

For one master:
Stay haproxy in hosts empty and delete ip address in master. Leave only init-master host.

For multi-master:
Set ip address in init-master, master and haproxy if it needed.

Both roles testing on vagrant centos7 box.
