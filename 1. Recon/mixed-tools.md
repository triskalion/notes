# nmap
#### Host Discovery
* `-n`: no DNS resolution
* `-Pn`: no ping (_ARP scan is still attempted_)
* `-sn`: only ping (_in reality it does TCP and UDP on port 80 and 443_)
* `--disable-arp-ping`
* `-PS/PA/PU/PY[portlist]`: TCP SYN/ACK, UDP or SCTP discovery to given ports
* P*
  - `PE/PP/PM`: ICMP echo, timestamp, and netmask request discovery probes
  - `PR` - arp scan; done by default with other P* options

#### Flags
* `-sN` - null scan; every bit 0
* `-sF` - FIN scan
* `-sX` - Christmas scan
<br>_the above flags "exploits" the fact that TCP RFC states that for packages without *SYN*,*RST* and *ACK* the target a *RST* for *closed* ports and *no response* for *open* ports._
<br>_ATTENTION! most OS send *RST in both cases*_
- `-sA` - determine presence of firewalls;
  - open/closed ports => *unfiltered*
  - no response ports => *filtered*

#### Stealth scans
* `-sI`: Idle Zombie scan
*  `-b`: FTP Bounce scan

#### Scan for vulnerabilities
* `--script vuln`


# hping3
#### Flags
* `-S` - SYN scan
* `-r` - displays IP ID increments relatively
#### Zombie Scan
- Find a zombie
  - `hping3 -S -r -p <target_port> <target_IP>` - where target = suspected zombie
- Idle Scan
  - `hping3 -a <zombie_IP> -S -p <target_port> <target_IP>`
 
#### Ping scan
  - `hping3 -1 <192.168.1.x> --rand-dest` - replace x with values

# arp-scan
#### Host Discovery
* `arp-scan -I eth1 >target/24>`

# fping
