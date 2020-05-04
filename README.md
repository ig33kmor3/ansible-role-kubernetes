# ansible-role-baseline

## Requirements

- Ubuntu 18.04 LTS

## Installation

Define in requirements.yml

```ansible
- src: https://github.com/ig33kmor3/ansible-role-kubernetes.git
  version: master
  name: kubernetes
```

Add to project:

```bash
ansible-galaxy install -r requirements.yml -f
```

## Configuration

Set variables in playbook for all

```yml
kcli_version: 1.18.2-00
k8s_version: 1.18.2
k8s_environment: bare-metal
```

Set variables in playbook for master only

```yml
kubernetes_role: master
cert_sans: ["k8s-master-001.geek.local", "k8s-master-001"]
pod_network_calico: https://docs.projectcalico.org/v3.11/manifests/calico.yaml
```

Set variables in playbook for workers only

```yml
kubernetes_role: worker
cert_sans: ["k8s-master-001.geek.local", "k8s-master-001"]
pod_network_calico: https://docs.projectcalico.org/v3.11/manifests/calico.yaml
```
