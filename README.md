[![Build Status](https://travis-ci.org/midonet/ansible-midonet-gateway.svg?branch=master)](https://travis-ci.org/midonet/ansible-midonet-gateway)


midonet-gateway
=============

Ansible role for midonet gateways.
Provides either a static or dynamic (BGP) setup for the edge networking.


Requirements
------------

Ubuntu Trusty, Ubuntu Xenial or RedHat/CentOS 7

Role Variables
--------------

* Required:

Keystone credentials.

* Not Required:

By default, the role will setup an static gateway with the default settings as
described in Midonet documentation.
To setup a BGP environment, a simple set of variables is needed, see example.
All variants create an external network, an edge router and all the virtual
topology required in a 'clean' deployment.

Dependencies
------------

Midonet repositories ( midonet.midonet-repos )
Midonet agent



Example Playbook
----------------

Static gateway:
```
- hosts: gateway
    roles:
      - role: midonet.midonet-gateway

```

BGP setup:
```
- hosts: gateway
    roles:
      - role: midonet.midonet-gateway
      midonet_gateway_bgp: True
      midonet_gateway_uplink_network: '10.88.88.0/24'
      midonet_gateway_uplinks:
        - iface: 'eth1'
          ip: '10.88.88.1'
      midonet_gateway_bgp_peers:
        - name: 'Peer1'
          ip: '10.88.88.2'
          remote_as: 4001
        - name: 'Peer2'
          ip: '10.88.88.3'
          remote_as: 4002

```


License
-------

Apache 2.0
