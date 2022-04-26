Ansible checkmk Agent Role
=========

An Ansible role to install and configure the checkmk monitoring agent along
with as few selected plugins.

Requirements
------------

A locally accessible checkmk install. See
[https://checkmk.com](https://checkmk.com) for more details.

Role Variables
--------------

This playbook exposes the following configuration variables:

* `checkmk_server` - hostname or IP address of your checkmk server
* `checkmk_site_name` - the name of your checkmk monitoring instance
* `checkmk_purge_xinetd` - purge the old xinetd package, since this role sets
   up agent access via SSH (defaults to true)

In addtion any hosts in the `docker_hosts` group will automatically have the
`mk_docker.py` agent plugin installed.

Dependencies
------------

None.

Example Playbook
----------------

User the role as follows:

```yaml
  - hosts: servers
    roles:
      - role: checkmk_agent
        checkmk_server: 127.0.0.1
        checkmk_site_name: mysite
```

License
-------

AGPLv3

Author Information
------------------

Rob Connolly [https://webworxshop.com](https://webworxshop.com)
