# Meterpreter
#### Route
* `meterpreter > run autoroute -s 10.2.31.0/24`
* background meterpreter
* `use auxiliary/server/socks_proxy`
* configure it according with `cat /etc/proxychains.conf`
* `run/exploit` socks_proxy
* in linux host use `proxychains nmap -sT ...`

## Cool resources
https://book.hacktricks.xyz/tunneling-and-port-forwarding