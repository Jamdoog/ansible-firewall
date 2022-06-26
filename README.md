Ansible Role: Firewall
=========

A ansible role to deploy a firewall on Debian/Ubuntu, RHEL/CentOS and OpenSUSE systems.

Future Intentions
-----------------

I would like to make this role better in a lot of ways:

- Remove custom firewall rules ability (probably with tags?)
- Ensure no disruption when running the script.
- Cleanliness could be improved.

Requirements
------------

While this role will automatically install it, if you use RHEL based, you will need the libselinux-python3 package. 

Role Variables
--------------

```yaml
CUSTOM_FIREWALL_RULES:
  DNS:
    port: 53
    proto: udp
    state: present
  HTTP:
    port: 80
    proto: tcp
    state: present

SSH_PORT: 22
```


Dependencies
------------

No dependencies.

Example Playbook
----------------

```yaml
- hosts: firewall
  become: true

  vars:
    CUSTOM_FIREWALL_RULES:
      DNS:
        port: 53
        proto: udp
        state: present
      HTTP:
        port: 80
        proto: tcp
        state: present
SSH_PORT: 22

  roles:
    - role: jamdoog.firewall
```

License
-------

BSD

Author Information
------------------

This role was created by James Ledger, I write about things on https://jamesledger.net