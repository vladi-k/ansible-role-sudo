ansible-role-sudo
====

Install and configure sudo.

Requirements
------------

* Tested on RHEL8

Role Variables
--------------

* `sudo_packages` - list of sudo packages to install
* `sudo_files` - list of sudo files to create, example:
```yaml
sudo_files:
  - name: jsmith
    user: jsmith
    host: "{{ inventory_hostname }}"
    runas: root
    nopassword: true
    commands: whoami
```

Dependencies
------------

Collections:

* `community.general` >= 6.3.0


Example Playbook
----------------

```yaml
- hosts: my_servers
  vars:
    sudo_files:
      - name: jsmith
        user: jsmith
        host: "{{ inventory_hostname }}"
        runas: root
        nopassword: true
        commands: whoami
  roles:
    - ansible-role-sudo
```

License
-------

GPLv3

Author Information
------------------

Vladimir Vasilev (@vladi-k)
