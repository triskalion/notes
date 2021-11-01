# nslookup
_During tests, it was observed that when needed to scan a domain with a specific DNS server, the syntax `nslookup <domain> - <DNS server>`doesn't return results.
	Instead, if used with specific query `-q=<MX,NS etc.>`, it will returned results._<br>
## NS enumeration
1. nslookup -q=NS `<domain>`  - `<DNS server>`
2. 
* nslookup
* server `<DNS server>`
* set q=NS
* `<domain>`

### MX enumeration
* -q=NS


##Zone Transfer