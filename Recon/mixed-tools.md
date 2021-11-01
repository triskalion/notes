# nmap
#### Host Discovery
* `-n`: no DNS resolution
* `-Pn`: no ping (_ARP scan is still attempted_)
* `sn`: only ping (_in reality it does TCP and UDP on port 80 and 443_)
* `-PS/PA/PU/PY[portlist]`: TCP SYN/ACK, UDP or SCTP discovery to given ports
* `PE/PP/PM`: ICMP echo, timestamp, and netmask request discovery probes
