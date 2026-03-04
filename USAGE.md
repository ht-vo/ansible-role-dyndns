# Usage Guide

This document provides detailed instructions on how to use `ansible-role-dyndns`.

## Installation

* Add the following block to your `requirements.yml`:

```yaml
---
- src: https://github.com/ht-vo/ansible-role-dyndns.git
  name: hl.dyndns
  version: v1.0.0
...
```

## Playbook

* Create a `playbook.yml`:

```yaml
- hosts: localhost
  become: false
  gather_facts: false
  vars:
    dyndns_hostname: 'home.domain.tld'
    ovh_username: 'user'
    ovh_password: 'password'
  roles:
    - role: hl.dyndns
...
```

## Execution Commands

1. **Update** dynamic DNS record:

```shell
ansible-playbook ./playbook.yml
```
