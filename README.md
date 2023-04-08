# Ansible Role: Chrony

![CI](https://github.com/acavella/ansible-role-chrony/actions/workflows/ci.yml/badge.svg)
![GitHub last commit](https://img.shields.io/github/last-commit/acavella/ansible-role-chrony)
![GitHub repo size](https://img.shields.io/github/repo-size/acavella/ansible-role-chrony)

An Ansible Role to install and configure the chrony daemon on Linux.

## Requirements

| Name | Version | Notes |
| ----- | ----- | ----- |
| Red Hat Enterprise Linux | 8.x | NA |
| Ansible | 2.9+ | NA |

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

```yaml
# Public ethernet adapter
public_ethernet_interface: eth0

# Port that must be accessible via public
wireguard_port: 51820
```

Private and public keys used to define initial server and client configurations.

```yaml
server_private_key_encoded:  set to generated wireguard server private key, base64 encoded.
client_public_key_encoded:   set to generated wireguard client public key, base64 encoded.
server_private_key_decoded:  base64 decoded version of above key, used in wg0.conf.j2
client_public_key_decoded:   base64 decoded version of above key, used in wg0.conf.j2
```

## Dependencies

None.

## Example Playbook

```yaml
- hosts: myserver
    roles:
      - { role: acavella.wireguard }
```
## License

GNU General Public License v3.0

## Author Information

This role was created in 2021 by [Tony Cavella](https://www.cavella.com/)
