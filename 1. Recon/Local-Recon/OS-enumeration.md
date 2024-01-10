## Linux
* Network Info
   * `ifconfig` or `ip a`
   * `arp -a/-en`	
   * `route -n`
   * `netstat -ltpn` - TCP
   * `netstat -lupn` - UDP
   * `netstat -auntp`
   * `ss -twurp` 
   * `traceroute -n <IP>` - how many hops are between machines
   * `cat /etc/resolv.conf` - DNS information
   * https://staaldraad.github.io/2017/12/20/netstat-without-netstat/
   * `nmap -sT -p4444-4450 portquiz.net` - check outbound port connectivity
* List all
   * `ls -las /root`
* OS
   * `cat /proc/version`
   * `lscpu` - architecture
   * `lsb_release` - OS
   * `uname -a`
   * `cat /etc/issue` - OS
   * `cat /etc/*-release` - OS
   * `lastlog`
   * `w` - who is currently logged onto the system
   * `last` - last logged on users
   * `for user in $(cat /etc/passwd | cut -f1 -d":"); do id $user; done` - all users including UID and GID
   * `cat /etc/passwd | cut -f1,3,4 -d":" | grep "0:0" | cut -f1 -d":" | awk {print $1}` - list all UID 0 (root) accounts
   * `sudo -l` - what can we do without a password
   	* `sudo -l | grep vim/nmap/vi` 
   * `cat /root/.bash_history`
   * `find /home/* -name *.*history -print 2> /dev/null` - read other users *.bash_history*
   * `echo $PATH`
   * `cat /etc/crontab && ls -als /etc/cron*` - list all cron jobs
   * `find /etc/cron* -type f -perm -o+w -exec ls -l {} \;` - find world writeable cron jobs
   * `find /etc/init.d ! -uid 0 -type f 2>/dev/null | xargs ls -la` - check service configs readable or modifiable by current user
   * `ps auxwww` - list running processes
   * `ps -u root` - list processes running as root
   * `ps -u $USER` - list processes running as current user
   * `find / -perm -4000 -type f 2>/dev/null` - find SUID files
   * `find / -uid 0 -perm -4000 -type f 2>/dev/null` - find SUID files owned by root
   * `find / -perm -2000 -type f 2>/dev/null` - find GUID files
   * `find / -perm -2 -type f 2>/dev/null` - find world-writeable files
   * `ls -al /etc/*.conf`
   * `grep pass* /etc/*.conf`
   * `lsof -n` - list open files
   * `ps aux | awk '{print $11}' | xargs -r ls -la 2>/dev/null | awk '!x[$0]++'` - print process binaries/paths and permissions
   * SUID/GUID files
   * GTFO bin SUID/GUID execs
   * strings SUID/GUID execs
   * PATH variable manipulation
* User Enum
   * `id`
   * `cat /etc/passwd`
   * `cat /etc/shadow`
   * `cat /etc/group`
   * `cat /etc/sudoers`
* Password hunting
  * `grep --color=auto -rnw '/' -ie "PASSWORD" --color=always 2> /dev/null` - search in files
  * `grep "password" /etc/*.conf 2> /dev/null` - search password in conf files
  * `locate password | more` - search file name
  * `find / -name id_rsa 2> /dev/null`
### Tools
* LinEnum - https://github.com/rebootuser/LinEnum
* LinuxPrivChecker - https://github.com/sleventyeleven/linuxprivchecker
* Unix-privesc-check - https://pentestmonkey.net/tools/audit/unix-privesc-check
* mimipenguin - https://github.com/huntergregal/mimipenguin - dumps the logon for currently logged on user

## Windows
* Network info
  * ipconfig /all
  * arp -a
  * route print
  * netstat -ano
* List all
  * `dir /r`
* Systeminfo
  * `systeminfo | findstr /B /I /C:"OS Name" /C:"Os Version" /C:"System Type"`
* See patches and filter columns
  * `wmic qfe get caption,description,providername`
* See logical disks info
  * `wmic logicaldisk get caption,description,providername`
* User details
  * `whoami`
  * `whoami /priv`
  * `whoami /groups`
* User and group details
  * `net user <user>`
  * `net localgroup <group>`
* Password hunting
  * `findstr /si password *.txt *.ini *.config` - searches in current folder
* Firewall and A/V enumeration
  * `sc query windefend` - Windows defender status
  * `sc queryex type=service` - service status
  * `netsh advfirewall firewall dump` - old command
  * `netsh firewall show state`
  * ` netsh firewall show config`
* Read secondary data streams - **hm.txt:root.txt:$DATA**
  *  Powershell: `powershell (Get-Content *<primary-stream>* -Stream <secondary-stream>)`
  *  Regular cmd: `more < <primary-stream>:<secondary-stream>:$DATA`
 ### Tools
 * Windows-privesc-check - https://code.google.com/archive/p/windows-privesc-check/wikis/DesignGoals.wiki

## Resources
* https://blog.g0tmi1k.com/2011/08/basic-linux-privilege-escalation/
