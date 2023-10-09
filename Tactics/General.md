1. nmap IP and look for interesting ports/services
2. SMB/RPC -> read shares, mount shares
3. search for vulnerable versions

PrivEsc
1. sudo -l
2. SUID/GUID files
3. GTFO bin SUID/GUID execs
4. strings SUID/GUID execs
* PATH variable manipulation
### Get host info
* `nmap -sU -p 161 --script=snmp-info <target>`
* `nmap -sU -p 161 --script=snmp-interfaces <target>`
* `nmap -sU -p 161 --script=snmp-netstat <target>`
* `nmap -sU -p 161 --script=snmp-sysdescr <target>`
* `nmap -sU -p 161 --script=snmp-win32-users <target>`
* nmap -sU -p 161 -sC <target>
  * ![#f03c15] (Performs a script scan using the default set of scripts. It is equivalent to --script=default. Some of the scripts in this category are considered intrusive and should not be run against a target network without permission.)

### Wordlists
* `/usr/share/metasploit-framework/data/wordlists/unix_passwords.txt`
* `/usr/share/wordlists/seclists`
