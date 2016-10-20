[![Build Status](https://travis-ci.org/midonet/ansible-midonet-gateway.svg?branch=master)](https://travis-ci.org/midonet/ansible-midonet-gateway)


midonet-gateway
=============

Ansible role for midonet gateways.
Provides either a static or dynamic (BGP) setup for the edge networking.


Requirements
------------

Ubuntu or RedHat/CentOS

Role Variables
--------------

* Required:

`foobar` Some variable.

* Not Required:


Dependencies
------------

Midonet repositories ( midonet.midonet-repos )
Midonet agent



Example Playbook
----------------

```
- hosts: gateway
    roles:
      - role: midonet.midonet-gateway

```

License
-------

Apache 2.0
