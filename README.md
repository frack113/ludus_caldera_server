# Ansible Role: Caldera Server

An Ansible Role that installs [Caldera Server](https://caldera.mitre.org/) main branch on linux .


## Requirements

- Linux server
  - Debian 12
  - Ubuntu 24 LTS
- Internet connection

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    # The go version to install for plugins
    ludus_caldera_go_version: '1.23.4'

    # User 
    ludus_caldera_admin_pwd: 'admin'
    ludus_caldera_red_pwd: 'red'
    ludus_caldera_blue_pwd: 'blue'

    # Network Config
    ludus_caldera_dns_socket: 8853
    ludus_caldera_ftp_port: 2222
    ludus_caldera_http: 8888
    ludus_caldera_tcp: 7010
    ludus_caldera_udp: 7011
    ludus_caldera_websocket: 8888
    ludus_caldera_port: 8888

    # Plugins
    ludus_caldera_plugins:
      - access
      - atomic
      - sandcat

## Dependencies

None.

## Example Playbook


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
    role_vars:
      ludus_caldera_plugins:
        - access
        - atomic
        - human
        - sandcat
```

## License

[//]: # (If you change the License type, be sure to change the actual LICENSE file as well)
GPLv3

## Author Information

This role was created by [frack113](https://github.com/frack113), for [Ludus](https://ludus.cloud/).
