# Ansible Role: Caldera Server

An Ansible Role that installs [Caldera Server](https://caldera.mitre.org/) main branch on linux .


## Requirements

- Ubuntu LTS server
- Internet connection

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    # The go version to install for plugins
    ludus_caldera_go_version: '1.23.4'

    # Password 
    ludus_caldera_admin_pwd: 'admin'
    ludus_caldera_red_pwd: 'red'
    ludus_caldera_blue_pwd: 'blue'


## Dependencies

None.

## Example Playbook

```yaml
- hosts: caldera-server
  roles:
    - frack113.ludus_caldera_server
  vars:
    ludus_aurora_dashboard: true
```

## Example Ludus Range Config

```yaml
ludus:
  - vm_name: "{{ range_id }}-Caldera"
    hostname: "{{ range_id }}-Caldera"
    template: ubuntu-24.04-x64-server-template
    vlan: 99
    ip_last_octet: 2
    ram_gb: 4
    cpus: 2
    linux: true
    roles:
      - frack113.ludus_caldera_server
```

## License

[//]: # (If you change the License type, be sure to change the actual LICENSE file as well)
GPLv3

## Author Information

This role was created by [frack113](https://github.com/frack113), for [Ludus](https://ludus.cloud/).
