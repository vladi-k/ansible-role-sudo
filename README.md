ansible-role-sudo
====

Install and configure sudo.

Requirements
------------

* RHEL8

Role Variables
--------------

* `sudo_packages` - list of sudo packages to install
* `sudo_visudo_path` - path to visudo
* `sudo_users` - list of sudo users, example:
```yaml
sudo_users:
  - name: zabbix
    hosts: "{{ inventory_hostname }}"
    runas: root
    options: "NOPASSWD:"
    commands: /usr/sbin/smartctl
```

Dependencies
------------

N/A


Example Playbook
----------------

```yaml
- hosts: my_servers
  vars:
    sudo_users:
      - name: zabbix
        hosts: "{{ inventory_hostname }}"
        runas: root
        options: "NOPASSWD:"
        commands: /usr/sbin/smartctl
  roles:
    - ansible-role-sudo
```

License
-------

GPLv3

Author Information
------------------

Vladimir Vasilev (@vladi-k)
