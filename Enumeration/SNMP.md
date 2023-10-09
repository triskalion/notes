# SNMP
<br><br>Ports:
- UDP 161
- UDP 162

  ### Get host info
* `nmap -sU -p 161 --script=snmp-info <target>`
* `nmap -sU -p 161 --script=snmp-interfaces <target>`
* `nmap -sU -p 161 --script=snmp-netstat <target>`
* `nmap -sU -p 161 --script=snmp-sysdescr <target>`
* `nmap -sU -p 161 --script=snmp-win32-users <target>`
* nmap -sU -p 161 -sC <target>
  * ![#f03c15] (Performs a script scan using the default set of scripts. It is equivalent to --script=default. Some of the scripts in this category are considered intrusive and should not be run against a target network without permission.)

#### Bruteforce
* `nmap -sU --script snmp-brute 10.2.16.153 --script-args snmp-brute.communitiesdb=/usr/share/wordlists/seclists/Discovery/SNMP/common-snmp-community-strings.txt`


## Cool resources
