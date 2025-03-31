# ansible-k8s-crio

This repository contains ansible role which installs cri-o, kubelet and kubeadm on specific hosts.

## Variables

- `crio_version`: Version of CRI-O to install (default: `v1.32`).
- `kubernetes_version`: Version of Kubernetes tools to install (default: `v1.32`).

## Usage

```bash
ansible-playbook playbook.yml -J <vault_password>
```

`<vault_password>` is the same password used for master, worker1, worker2 hosts.

## License

The project is licensed under an [Unlicense](LICENSE).
