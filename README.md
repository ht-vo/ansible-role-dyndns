# ansible-role-dyndns

This Ansible role updates Dynamic DNS records to keep your domain pointing to a changing home or office IP address.

## Requirements

* Have a registered domain name with supported DNS provider

### OVHcloud

> [!TIP]
> Refer to the [OVHcloud KB0051641](https://help.ovhcloud.com/csm/en-ie-dns-dynhost?id=kb_article_view&sysparm_article=KB0051641) for a step-by-step walkthrough of the DynHost setup.

You must configure your **DynHost settings** in the OVHcloud Control Panel:

1. Create a **DynHost identifier** (a dedicated username and password)

2. Create a **DynHost Record** (e.g., `home.domain.tld`)

## Role Variables

* Common Configuration

| Variable               | Description                                             | Default                      |
|------------------------|---------------------------------------------------------|------------------------------|
| `dyndns_provider`      | Set the DNS provider to use (currently supports  `ovh`) | `ovh`                        |
| `dyndns_hostname`      | Set the target FQDN (e.g., home.domain.tld)             | `''`                         |
| `dyndns_ip_lookup_url` | Set the service URL used to discover your public IPv4   | `https://ipv4.icanhazip.com` |

* OVHcloud DynHost

Required only when `dyndns_provider` is set to `ovh`.

| Variable       | Description                      | Default                                               |
|----------------|----------------------------------|-------------------------------------------------------|
| `ovh_api_url`  | Set the OVH DynHost API endpoint | `https://dns.eu.ovhapis.com/nic/update?system=dyndns` |
| `ovh_username` | Set the OVH DynHost username     | `''`                                                  |
| `ovh_password` | Set the OVH DynHost password     | `''`                                                  |

## Getting Started

For detailed installation steps, please refer to the **[usage guide](USAGE.md)**.

## Development

Interested in the roadmap? Check the **[to-do list](TODO.md)**.

## License

This project is [MIT](LICENSE) licensed.
