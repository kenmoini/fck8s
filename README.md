# Fedora CoreOS Kubernetes

This repo sets up a Kubernetes cluster with Fedora CoreOS on Libvirt

## Prerequisites

### [One-time] Installing Pip modules

Some of the Ansible Modules require additional Python Pip modules - install the following:

```bash
## Install Ansible if needed
sudo python3 -m pip install ansible paramiko

## Install the Kubernetes and OpenShift modules
sudo python3 -m pip install kubernetes openshift
```

### [One-time] Installing Ansible Collections

In order to run this Playbook you'll need to have the needed Ansible Collections already installed - you can do so easily by running the following command:

```bash
ansible-galaxy collection install -r collections/requirements.yml
```

## Deploying

The full Kubernetes stack can easily be deployed with:

```bash
ansible-playbook ansible/bootstrap.yml
```

## Destroying

The VMs can be destroyed from the Libvirt host via:

```bash
ansible-playbook ansible/delete_vms.yml
```

## TODO: Kubernetes Cluster Workloads

The following can be deployed:

- Flannel
- MetalLB
- nginx-ingress