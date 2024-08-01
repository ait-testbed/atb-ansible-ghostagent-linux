Ansible role to install ghostserver
===================================

This role installs a [ghosts agent on Linux](https://github.com/cmu-sei/GHOSTS)

Requirements
------------

A linux distribution 

Role Variables
--------------

```yaml
ghostagent_packages:
 - dotnet-sdk-8.0

ghostsagent_user: "ubuntu"
ghostagent_path: "/home/{{ ghostsagent_user }}/"
```

Dependencies
------------

None

Example Playbook
----------------


```yaml
- name: Install ghosts-agent
  hosts: all
  roles:
    - role: atb-ansible-ghostagent
```

License
-------

GPL-3.0

Author Information
------------------

Wolfgang Hotwagner
