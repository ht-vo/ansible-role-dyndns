# ansible-role-dyndns

> :warning: **Disclaimer**: Currently, only the OVHcloud provider is supported.

This Ansible role is used to update a Dynamic DNS (DDNS/DynHost) record.

## Requirements

- A registered domain name with [OVHcloud](https://www.ovhcloud.com)

- A configured DynHost, follow this [KB](https://help.ovhcloud.com/csm/en-ie-dns-dynhost?id=kb_article_view&sysparm_article=KB0051641):

    - 1 - Create a DynHost username

    - 2 - Create the dynamic DNS record

## Usage

- requirements.yaml

```yaml
---
- src: https://github.com/ht-vo/ansible-role-dyndns.git
  name: hl.dyndns
  version: v1.0.0
...
``` 

- playbook.yaml

```yaml
---
- hosts: localhost

  vars:
    domain_name: ''
    ovh_dynhost_hostname: ''
    ovh_dynhost_username: ''
    ovh_dynhost_password: ''
    ovh_dynhost_state: 'present'

  roles:
    - role: hl.dyndns
...
```

## License

This project is [MIT](https://github.com/ht-vo/ansible-role-dyndns/blob/main/LICENSE) licensed.