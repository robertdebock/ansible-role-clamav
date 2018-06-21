clamav
=========

[![Build Status](https://travis-ci.org/robertdebock/ansible-role-clamav.svg?branch=master)](https://travis-ci.org/robertdebock/ansible-role-clamav)

Provides ClamAV for your system.

Context
--------
This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://robertdebock.nl/) for further information.

Here is an overview of related roles:
![dependencies](https://raw.githubusercontent.com/robertdebock/drawings/artifacts/clamav.png "Dependency")

Requirements
------------

- Access to a repository containing packages, likely on the internet.
- The repository EPEL (for CentOS/RHEL systems). This dependency is managed by an explicit reference to `robertdebock.epel` in meta/main.yml.

Role Variables
--------------

- clamav_tcpsocket: 10025
- clamav_tcpaddr: 127.0.0.1

Dependencies
------------

Use these roles to prepare your system for this role:

- [robertdebock.bootstrap](https://travis-ci.org/robertdebock/ansible-role-bootstrap)
- [robertdebock.epel](https://travis-ci.org/robertdebock/ansible-role-epel)

Download the dependencies by issuing this command:
```
ansible-galaxy install --role-file requirements.yml
```

Compatibility
-------------

This role has been tested against the following distributions and Ansible version:

|distribution|ansible 2.3|ansible 2.4|ansible 2.5|
|------------|-----------|-----------|-----------|
|alpine-latest|yes|yes|yes|
|alpine-edge|yes|yes|yes|
|archlinux|no|no|no|
|centos-6|yes|yes|yes|
|centos-latest|yes|yes|yes|
|debian-stable|yes|yes|yes|
|debian-sid|yes|yes|yes|
|debian-latest|yes|yes|yes|
|debian-wheezy|yes|yes|yes|
|fedora-latest|yes|yes|yes|
|fedora-rawhide|yes|yes|yes|
|opensuse-leap|yes|yes|yes|
|opensuse-tumbleweed|yes|yes|yes|
|ubuntu-artful|yes|yes|yes|
|ubuntu-latest|yes|yes|yes|

Example Playbook
----------------

```
- hosts: servers

  roles:
    - role: robertdebock.bootstrap
    - role: robertdebock.epel
    - role: robertdebock.clamav
      clamav_tcpsocket: 10025
      clamav_tcpaddr: 127.0.0.1
```

Install this role using `galaxy install robertdebock.clamav`.

License
-------

Apache License, Version 2.0

Author Information
------------------

Robert de Bock](https://robertdebock.nl/) <robert@meinit.nl>
