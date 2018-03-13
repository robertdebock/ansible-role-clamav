clamav
=========

[![Build Status](https://travis-ci.org/robertdebock/ansible-role-clamav.svg?branch=master)](https://travis-ci.org/robertdebock/ansible-role-clamav)

Provides ClamAV for your system.

Context
--------
This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://robertdebock.nl/) for further information.

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

- robertdebock.bootstrap
- robertdebock.epel

Download the dependencies by issuing this command:
```
ansible-galaxy install --role-file requirements.yml
```

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

Robert de Bock <robert@meinit.nl>
