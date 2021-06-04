### Linux
1. General
	* `ifconfig` or `ip a`
	* `arp -a`	
	* `route`
	* `netstat -ltpn` - TCP
	* `netstat -lupn` - UDP
2. List all
	* `ls -la`
3. OS
	* ` cat /proc/version`
	* `/etc/issue` - distribution
	* `lscpu` - architecture
4. User Enum
	* `id`
	* `sudo -l`
	* `cat /etc/passwd`
	* `cat /etc/shadow`
	* `cat /etc/group`
5. Password hunting
	* `grep --color=auto -rnw '/' -ie "PASSWORD" --color=always 2> /dev/null` - search in files
	* `locate password | more` - search file name
	* `find / -name id_rsa 2> /dev/null`

### Windows
1. General
	* ipconfig /all
	* arp -a
	* route print
	* netstat -ano
2. List all
	* `dir /r`
2. Systeminfo
	* `systeminfo | findstr /B /I /C:"OS Name" /C:"Os Version" /C:"System Type"`
3. See patches and filter columns
	* `wmic qfe get caption,description,providername`
4. See logical disks info
	* `wmic logicaldisk get caption,description,providername`
5. User details
	* `whoami`
	* `whoami /priv`
	* `whoami /groups`
6. User and group details
	* `net user <user>`
	* `net localgroup <group>`
7. Password hunting
	* `findstr /si password *.txt *.ini *.config` - searches in current folder
8. Firewall and A/V enumeration
	* `sc query windefend` - Windows defender status
	* `sc queryex type=service` - service status
	* `netsh advfirewall firewall dump` - old command
	* `netsh firewall show state`
	* ` netsh firewall show config`
3. Read secondary data streams - **hm.txt:root.txt:$DATA**
	*  Powershell: `powershell (Get-Content *<primary-stream>* -Stream <secondary-stream>)`
	*  Regular cmd:	`more < <primary-stream>:<secondary-stream>:$DATA`
