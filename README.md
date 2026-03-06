# [Ansible role checkmk_agent](#ansible-role-checkmk_agent)

Install the checkmk agent and a selection of plugins

|GitHub|GitLab|Downloads|Version|
|------|------|---------|-------|
|[![github](https://github.com/buluma/ansible-role-checkmk_agent/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-checkmk_agent/actions)|[![gitlab](https://gitlab.com/shadowwalker/ansible-role-checkmk_agent/badges/master/pipeline.svg)](https://gitlab.com/shadowwalker/ansible-role-checkmk_agent)|[![downloads](https://img.shields.io/ansible/role/d/buluma/checkmk_agent)](https://galaxy.ansible.com/buluma/checkmk_agent)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-checkmk_agent.svg)](https://github.com/buluma/ansible-role-checkmk_agent/releases/)|

## [Example Playbook](#example-playbook)

This example is taken from [`molecule/default/converge.yml`](https://github.com/buluma/ansible-role-checkmk_agent/blob/master/molecule/default/converge.yml) and is tested on each push, pull request and release.

```yaml
---
- become: true
  gather_facts: true
  hosts: all
  name: Converge
  pre_tasks:
  - ansible.builtin.apt:
      cache_valid_time: 600
      update_cache: true
    changed_when: false
    name: Update apt cache.
    when: ansible_os_family == 'Debian'
  roles:
  - checkmk_server: 127.0.0.1
    checkmk_site_name: mysite
    role: buluma.checkmk_agent
  vars:
    checkmk_purge_xinetd: true
```

The machine needs to be prepared. In CI this is done using [`molecule/default/prepare.yml`](https://github.com/buluma/ansible-role-checkmk_agent/blob/master/molecule/default/prepare.yml):

```yaml
---
- become: true
  gather_facts: false
  hosts: all
  name: Prepare
  roles:
  - role: buluma.bootstrap
```

Also see a [full explanation and example](https://buluma.github.io/how-to-use-these-roles.html) on how to use these roles.

## [Role Variables](#role-variables)

The default values for the variables are set in [`defaults/main.yml`](https://github.com/buluma/ansible-role-checkmk_agent/blob/master/defaults/main.yml):

```yaml
---
checkmk_pub_key: ""
checkmk_purge_xinetd: true
checkmk_server: localhost
checkmk_site_name: cmk
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/buluma/ansible-role-checkmk_agent/blob/master/requirements.txt).

## [State of used roles](#state-of-used-roles)

The following roles are used to prepare a system. You can prepare your system in another way.

| Requirement | GitHub | GitLab |
|-------------|--------|--------|
|[buluma.bootstrap](https://galaxy.ansible.com/buluma/bootstrap)|[![Build Status GitHub](https://github.com/buluma/ansible-role-bootstrap/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-bootstrap/actions)|[![Build Status GitLab](https://gitlab.com/shadowwalker/ansible-role-bootstrap/badges/master/pipeline.svg)](https://gitlab.com/shadowwalker/ansible-role-bootstrap)|
|[buluma.python_pip](https://galaxy.ansible.com/buluma/python_pip)|[![Build Status GitHub](https://github.com/buluma/ansible-role-python_pip/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-python_pip/actions)|[![Build Status GitLab](https://gitlab.com/shadowwalker/ansible-role-python_pip/badges/master/pipeline.svg)](https://gitlab.com/shadowwalker/ansible-role-python_pip)|
|[buluma.repo_epel](https://galaxy.ansible.com/buluma/repo_epel)|[![Build Status GitHub](https://github.com/buluma/ansible-role-repo_epel/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-repo_epel/actions)|[![Build Status GitLab](https://gitlab.com/shadowwalker/ansible-role-repo_epel/badges/master/pipeline.svg)](https://gitlab.com/shadowwalker/ansible-role-repo_epel)|

## [Context](#context)

This role is part of many compatible roles. Have a look at [the documentation of these roles](https://buluma.github.io/) for further information.

Here is an overview of related roles:
![dependencies](https://raw.githubusercontent.com/buluma/ansible-role-checkmk_agent/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/buluma):

|container|tags|
|---------|----|
|[Alpine](https://hub.docker.com/r/buluma/alpine)|all|
|[Amazon](https://hub.docker.com/r/buluma/amazonlinux)|all|
|[EL](https://hub.docker.com/r/buluma/enterpriselinux)|all|
|[Debian](https://hub.docker.com/r/buluma/debian)|all|
|[Fedora](https://hub.docker.com/r/buluma/fedora)|all|
|[opensuse](https://hub.docker.com/r/buluma/opensuse)|all|
|[Ubuntu](https://hub.docker.com/r/buluma/ubuntu)|all|

The minimum version of Ansible required is 2.12, tests have been done on:

- The previous version.
- The current version.
- The development version.

If you find issues, please register them on [GitHub](https://github.com/buluma/ansible-role-checkmk_agent/issues).

## [License](#license)

[Apache-2.0](https://github.com/buluma/ansible-role-checkmk_agent/blob/master/LICENSE).

## [Author Information](#author-information)

[buluma](https://buluma.github.io/)

