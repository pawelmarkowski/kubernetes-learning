# Quick Start

## Install prerequisites

Please verify that you have properly installed the [prerequisites](./prerequisites.md).

## Install K8s using ansible 

If you want to enable customized list of modules you can do it by defining proper vars kubernetes-learning/ansible/inventories/training/group_vars/all.yml

Install requirements (ansible role [microk8s](https://github.com/pawelmarkowski/ansible-microk8s)) using ansible-galaxy.

```bash
ansible-galaxy role install -r ansible/playbooks/roles/requirements.yml --force
```

Run playbook (on localhost)

```bash
ansible-playbook -i ansible/inventories/training/hosts.yml ansible/playbooks/microk8s.yml --extra-vars "variable_host=localhost" -K
```

and voilà! MicroK8s is up, and running!

## Configure kubectl (K8s command line tool)

if you have config print: microk8s config and add it to .kube/config manually

```bash
cd $HOME
mkdir .kube
cd .kube
microk8s config > config
```

optionally, but I do not recommend that - you can specify alias for microk8s kubectl command:
```bash
vi ~/.bashrc
alias mkctl="sudo microk8s kubectl"
```

you can also specify default namespace
```bash
kubectl config set-context --current --namespace=<insert-namespace-name-here>
```

if you have multiple contexts in your configuration file, you can switch context (different K8s clusters) using:
```bash
kubectl config use-context <contextname>
```