# ansible-role-baseline

## Requirements

- Ubuntu 18.04 LTS

## Installation

Define in requirements.yml

```ansible
- src: https://github.com/ig33kmor3/ansible-role-kubernetes.git
  version: master
  name: ig33kmor3.kubernetes
```

Add to project:

```bash
ansible-galaxy install -r requirements.yml -f
```

## Configuration

Set variables in playbook for all

```yml
kubernetes_dep_version: 1.18.2-00
kubernetes_version: 1.18.2
kubernetes_environment: bare-metal
```

Set variables in playbook for master only

```yml
kubernetes_role: master
certificate_sans: ["k8s-master-001.geek.local", "k8s-master-001"]
pod_network_calico: https://docs.projectcalico.org/v3.11/manifests/calico.yaml
```

Set variables in playbook for workers only

```yml
kubernetes_role: worker
```
