# Ansible Role: Chrony

![CI](https://github.com/acavella/ansible-role-chrony/actions/workflows/ci.yml/badge.svg)
![GitHub last commit](https://img.shields.io/github/last-commit/acavella/ansible-role-chrony)
![GitHub repo size](https://img.shields.io/github/repo-size/acavella/ansible-role-chrony)

An Ansible Role to install and configure the chrony daemon on Linux.

## Requirements

| Name | Version | Notes |
| ----- | ----- | ----- |
| Red Hat Enterprise Linux | 7,8,9 | NA |
| Ansible | 2.9+ | NA |

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

```yaml
# Specifies an NTP server which can be used as a time source.
chrony_ntp_servers: []
# Used to specify a pool of NTP servers rather than a single NTP server.
chrony_ntp_pools: []
# Specifies a symmetric association with an NTP peer instead of a client/server association with an NTP server.
chrony_ntp_peers: 
  - 192.168.0.11 iburst
  - 192.168.0.12 iburst
# Enables a local reference mode, which allows chronyd operating as an NTP server when no real time source is available.
chrony_is_local: true 
# Designate a particular subnet from which NTP clients are allowed to access the NTP server.
chrony_allow_networks:
  - 192.168.0.0/16
# Location of the file containing symmetric keys which are shared between NTP servers and clients, or peers.
chrony_keyfile: /etc/chrony.keys
```

## Dependencies

None.

## Example Playbook

```yaml
- hosts: localhost
  roles:
    - { role: acavella.chrony }
```
## License

GNU General Public License v3.0

## Author Information

This role was created in 2023 by [Tony Cavella](https://www.cavella.com/)
