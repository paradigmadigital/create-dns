# create-dns

Create or modify a DNS record in route53

# Role Variables

* `dns.zone`      : The DNS zone to modify
* `dns.record`    : The full DNS record to create
* `dns.type`      : The type of DNS record to create (Choices: A, CNAME, MX, AAAA, TXT, PTR, SRV, SPF, NS, SOA)
* `dns.ttl`       : The TTL to give the new record [Default: 3600 (one hour)]
* `dns.value`     : The new value when creating a DNS record.  List of values are allowed for non-alias records.  When deleting a record all values for the record must be specified or Route53 will not delete it.  [Default: None]
* `dns.overwrite` : Whether an existing record should be overwritten on create if values do not match [Default: None]
* `dns.wait`      : Wait until the changes have been replicated to all Amazon Route 53 DNS servers.  [Default: False]


# Example playbook

```yaml
- hosts: localhost
  connection: local
  gather_facts: no
  roles:
    - create-dns
```

# License

GPLv2

# Author Information
jamatute (jamatute@paradigma)
