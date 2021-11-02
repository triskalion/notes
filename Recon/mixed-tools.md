# nmap
#### Host Discovery
* `-n`: no DNS resolution
* `-Pn`: no ping (_ARP scan is still attempted_)
* `sn`: only ping (_in reality it does TCP and UDP on port 80 and 443_)
* `-PS/PA/PU/PY[portlist]`: TCP SYN/ACK, UDP or SCTP discovery to given ports
* `PE/PP/PM`: ICMP echo, timestamp, and netmask request discovery probes

#### Flags
* `-sN` - null scan; every bit 0
* `-sF` - FIN scan
* `-sX` - Christmas scan
<br>_the above flags "exploits" the fact that TCP RFC states that for packages without *SYN*,*RST* and *ACK* the target a *RST* for *closed* ports and *no response* for *open* ports._
<br>_ATTENTION! most OS send *RST in both cases*_
- `-sI` - idle zombie scan
- `-sA` - determine presence of firewalls;
  - open/closed ports => *unfiltered*
  - no response ports => *filtered*

