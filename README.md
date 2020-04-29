install-towercli
=========
A role to install tower-cli modules on a connected/disconnected enviroment.

Requirements
------------
Ansible 2.9 installed. The folowging packages version will be used:
  - ansible-tower-cli-3.3.2-1.el7.noarch.rpm
  - python2-click-6.7-8.el7at.noarch.rpm
  - python2-colorama-0.3.9-3.el7at.noarch.rpm


Role Variables
--------------
```
towercli_path: /tmp/towercli-install
towercli_repo: https://releases.ansible.com/ansible-tower-cli/rpm/epel-7-x86_64/
```

Example inventory
----------------

```
[towercli]
rhel7.bcnconsulting.com ansible_connection=local
```

Example Playbook
----------------

```
---
- hosts: towercli
  gather_facts: yes
  become: yes
  become_method: sudo
  become_user: root
  remote_user: ansible
  vars: 
    towerclipath: /root/test
  roles:
    - role: ../roles/install-towercli
```

License
-------

GPLv3

Author Information
------------------

silvinux - silvinux7@gmail.com

Source
---------
[How Do I Install Ansible Tower's Commandline Tool, tower-cli, Using RPM/YUM?](https://access.redhat.com/solutions/3938881)
