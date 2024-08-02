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


ghostsserver_url: "http://192.168.100.184:5000/api"
```

> **NOTE:** The `ghostsserver_url` has a default value. Remember to update it in the playbook with the actual ghostsserver address!

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
      vars:
        ghostsserver_url: "http://192.168.100.184:5000/api"
```

License
-------

GPL-3.0

Author Information
------------------

Wolfgang Hotwagner
