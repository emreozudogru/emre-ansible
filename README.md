# emre-ansible

An Ansible role collection for day-to-day infrastructure operations such as system updates, agent installation, firmware workflows, monitoring integration, and environment standardization.

> Maintainer note: This repository reflects Emre's operational automation approach and includes pragmatic task design based on real production needs.

## What is included

This repository contains multiple standalone role directories, each with its own `tasks/main.yml` (and optional `vars/` or `handlers/`).

Example roles:
- `update_yum` for package updates and baseline utilities.
- `install_zabbix` and `install_zabbix_proxy` for monitoring deployments.
- `add_host_to_zabbix` and `update_netbox` for inventory/monitoring integration.
- `update_win` and `update_win_app` for Windows update workflows.
- `trx-*` and `setup-trx` for TRX/device-specific operations.

## Requirements

- Ansible Core 2.13+ (recommended).
- Python 3 on the control node.
- SSH/WinRM connectivity to managed nodes.
- Required collections depending on roles (for example `ansible.posix`).

Install common dependencies:

```bash
ansible-galaxy collection install ansible.posix
```

## Suggested repository structure usage

Each directory is intended to be called as a role from your playbooks:

```yaml
- hosts: all
  become: true
  roles:
    - update_yum
    - install_zabbix
```

## Security and operations notes

- Review role tasks before running in production, especially firmware and full upgrade roles.
- Test changes in staging first.
- Use inventory group targeting to limit blast radius.

## Contributing

Please read [CONTRIBUTING.md](CONTRIBUTING.md) before opening pull requests.

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE).
