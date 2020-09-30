# ansible-k8scluster

## Description

This Ansible project contains all roles needed to create a 3 nodes Kubernetes cluster (1 master + 2 workers) running on CentOS 7.7 operating system. 

Tested in ansible 2.9.13.

## How to use

* Prepare 3 machines with CentOS 7.7 Operating System
* Git clone the repo.
* Go to SRC/ansible/inventory/group_vars/ and edit the following variables in vars.yml file:

  `K8S01_IP: "192.168.100.1"`

  `K8S02_IP: "192.168.100.2"`

  `K8S03_IP: "192.168.100.3"`

* Run k8s-prep role:

  `cd SRC/ansible`


  `ansible-playbook --ask-pass -i inventory/production playbooks/k8s-prep.yml`
  
 * Finally, run k8s-deploy role:
 
   `ansible-playbook --ask-pass -i inventory/production playbooks/k8s-deploy.yml`

After all this steps you can go to K8S01 server and check cluster status by running `kubectl get nodes`command as a k8s user.
