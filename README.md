Ansible role to install ghostserver
===================================

This role installs a [ghosts agent on Linux](https://github.com/cmu-sei/GHOSTS) and optionally starts it as a service on boot.

Requirements
------------

A linux distribution 

Role Variables
--------------

```yaml
ghostagent_packages:
 - dotnet-sdk-8.0

ghostagent_autostart: true  # Set this to false if you don't want to start ghosts as a service automatically
ghostsagent_user: "aecid"
ghostagent_path: "/home/{{ ghostsagent_user }}/ghosts-client-linux-v8.0.0"
ghostagent_timeline_file: "timeline.json.j2"

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
        ghostagent_autostart: false
```

As the ghostagent is registered as a systemd service, you can use the 
following commands for manual inspection:

```shell
systemctl enable ghostagent
systemctl disable ghostagent
systemctl start ghostagent
systemctl stop ghostagent 
systemctl restart ghostagent
systemctl status ghostagent
```

License
-------

GPL-3.0

Author Information
------------------

Wolfgang Hotwagner, Anna Erdi
