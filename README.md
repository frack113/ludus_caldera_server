# Ansible Role: Caldera Server

An Ansible Role that installs [Caldera Server](https://caldera.mitre.org/) main branch on linux .

## Requirements

- Linux server
  - Debian 12
  - Ubuntu 24 LTS
- Internet connection

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

```yaml
# SHA-1 hash of the commit
ludus_caldera_git: b24f6e7a99cab19cbf417009bda9b9c6c81abc31

# User password
ludus_caldera_admin_pwd: 'admin'
ludus_caldera_red_pwd: 'red'
ludus_caldera_blue_pwd: 'blue'
```

## Dependencies

Ansible :

- community.docker
- geerlingguy.docker

## Example Playbook

## Example Ludus Range Config

```yaml
ludus:
  - vm_name: "{{ range_id }}-Caldera"
    hostname: "{{ range_id }}-Caldera"
    template: debian-12-x64-server-template
    vlan: 20
    ip_last_octet: 2
    ram_gb: 4
    cpus: 2
    linux: true
    roles:
      - frack113.ludus_caldera_server
    role_vars:
      ludus_caldera_admin_pwd: 'SuperPassword'
```

## License

[//]: # (If you change the License type, be sure to change the actual LICENSE file as well)
GPLv3

## Author Information

This role was created by [frack113](https://github.com/frack113), for [Ludus](https://ludus.cloud/).
