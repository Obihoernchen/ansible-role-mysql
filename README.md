mysql
=========

[![Build Status](https://travis-ci.org/robertdebock/ansible-role-mysql.svg?branch=master)](https://travis-ci.org/robertdebock/ansible-role-mysql)

Provides mysql/mariadb for your system.

Context
--------
This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://robertdebock.nl/) for further information.

Here is an overview of related roles:
![dependencies](https://raw.githubusercontent.com/robertdebock/robertdebock.github.io/artifacts/mysql.png "Dependency")


Requirements
------------

Access to a repository containing packages, likely on the internet.

Role Variables
--------------

- mysql_bind_address: an address where MySQL must bind on.

Dependencies
------------

You can use this role to prepare your system:

- robertdebock.bootstrap

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
    - role: robertdebock.mysql

  tasks:
    - name: create database
      mysql_db:
        name: bobdata

    - name: create user
      mysql_user:
        name: bob
        password: 12345
        priv: '*.*:ALL'
```

Install this role using `galaxy install robertdebock.mysql`.

License
-------

Apache License, Version 2.0

Author Information
------------------

Robert de Bock <robert@meinit.nl>
