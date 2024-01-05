#### Port
- NFS UDP/TCP: 2049
    - NFS services uses *rpcbind*
- Portmapper TCP/UDP: 111, 32771
- Samba TCP/UDP: 135,137,138,139,445
#### nmap scripts
__NFS__
* `ls /usr/share/nmap/scripts | grep nfs`
* `--script nfs-ls,nfs-showmount,nfs-statfs`
__Portmapper (rpcbind)__
* `--script rpc-grind,rpcinfo -p 111` - scan RPC services 
#### Tools
__NFS__
* `showmount -e <IP>`
* `mount -t nfs <NFS server IP>:</home/bob> <local folder> -o nolock`
__Portmapper (rpcbind)__
* `rpcinfo -p <IP>`

__Samba__
* `mount -t cifs <\\\\SMB server IP\\folder> <local folder>`
* `--script smb-enum-users`
* `--script smb-enum-shares`
* `--script smb-ls`
* `--script smb-os-discovery`
* 
