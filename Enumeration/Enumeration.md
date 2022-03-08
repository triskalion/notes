# NetBIOS
Allow apps on different systems to communicate over LAN.
<br><br>Ports:
- UDP 137 -> name services (NetBIOS name -> IP)
- UDP 138 -> datagram services (send/receive)
- TCP 139 -> session services (establish communication)

### Windows
#### nbtstat
* `nbtstat -A <target_IP>`
from the results above, pay attention to the number between `<>`. This number identifies the service/type.</br>
e.g. `<20>` - Server Service

#### net view
* `net view <target_IP>` - list domains, computers and shared resources

#### net use
* `net use <local_drive> \\<target_IP>` - connect or disconnect a PC to a shared resource


### Linux
#### nbtscan
* `nbtscan -v <target_IP>` - NetBIOS info of machine. `<target_IP>` also works with CIDR notation.

# SMB
#### Enumerate shares and hostname
* `smbclient -L <target_IP>` - NULL session when providing no user
* `smbclient  \\\\<target_IP>\\<share>`
	* `-N` - don't ask password
	<br>
* `smbmap -H <target_IP>` - NULL session without -u
* `smbmap -H <target_IP> -R <share>`
	<br>
* `nmblookup -A <target_IP>`
* `enum4linux -n <target_IP>`
* `nmap --script=smb-enum* <target_IP>`

## Cool resources
https://book.hacktricks.xyz/pentesting/pentesting-smb