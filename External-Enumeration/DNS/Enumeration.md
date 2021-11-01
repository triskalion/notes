# nslookup
_During tests, it was observed that when needed to scan a domain with a specific DNS server, the syntax `nslookup <domain> - <DNS server>`doesn't return results.
	Instead, if used with specific query `-q=<MX,NS etc.>`, it will returned results._<br>
#### NS enumeration
1. `nslookup -q=NS <domain>  - <DNS server>`
2. Interactive
* `nslookup`
* `server <DNS server>`
* `set q=NS`
* `<domain>`

#### MX enumeration
* -q=MX

#### All entries
* -q=any

#### Zone Transfer
1. `nslookup -q=AXFR <domain>  - <DNS server>`
2. Interactive
* `nslookup`
* `server <DNS NS>`
* `ls -d <domain>`

# dig
#### NS enumeration
* `dig @<DNS server> <domain> NS`

#### All entries
* `dig @<DNS server> <domain> ANY`

#### Filtering
- `dig @<DNS server> <domain> ANY <filtering>`
	<br>where _filtering_ can be
  - `+noall`
  - `+answer`
  - `+trace`
  - etc.

_**dig** and **nslookup** take default DNS from /etc/resolv.conf `nameserver <IP>` setting_


# fierce

# dnsenum

# dnsmap

# dnsrecon

# dnsdumpster