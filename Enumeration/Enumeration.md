# NetBIOS
Allow apps on different systems to communicate over LAN.
<br>Ports:
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