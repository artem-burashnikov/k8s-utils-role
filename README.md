# ansible-k8s-crio

This repository includes ansible role which installs **cri-o**, **kubelet** and **kubeadm** on Ubuntu hosts.

## Variables

- `crio_version`: Version of CRI-O to install (default: `v1.32`).
- `kubernetes_version`: Version of Kubernetes tools to install (default: `v1.32`).

## Roles structure

```ignorelang
roles/
├── common                # A common reusable role that installs a package.
│   ├── defaults
│   │   └── main.yml
│   ├── meta
│   │   └── main.yml
│   └── tasks
│       └── main.yml
├── crio
│   ├── defaults
│   │   └── main.yml
│   ├── meta
│   │   └── main.yml
│   ├── tasks
│   │   └── main.yml
│   └── vars
│       └── main.yml
└── k8s_tools
    ├── defaults
    │   └── main.yml
    ├── meta
    │   └── main.yml
    ├── tasks
    │   └── main.yml
    └── vars
        └── main.yml
```

## Usage

> [!IMPORTANT]
> You need to set up `root` access on your servers/VMs/etc.

1. By default Ansible uses OpenSSH. You can read more [here][1].
   Make sure you have public keys set up.
   Alternatively use encrypted password with `sshpass` package.

2. If you have SSH keys set up run playbook with:

    ```bash
    ansible-playbook -i inventory.yml playbook.yml
    ```

## License

The project is licensed under an [Unlicense](LICENSE).

<!---------------------------------------------------------------------------->

[1]: https://docs.ansible.com/ansible/latest/inventory_guide/connection_details.html "Ansible connection details."
