1. nmap IP and look for interesting ports/services
2. SMB/RPC -> read shares, mount shares
3. search for vulnerable versions

### RDP
* `rdesktop IP`
* `xfreerdp /u:”DOMAIN\USER” /p:”Pass” /v:IP`

### Wordlists
* `/usr/share/metasploit-framework/data/wordlists/unix_passwords.txt`
* `/usr/share/wordlists/seclists`

### Shells
* `/usr/share/webshells/`
* `/usr/share/laudanum`
* https://pentestmonkey.net/cheat-sheet/shells/reverse-shell-cheat-sheet

## Precompiled binaries
#### STatic nmap (no nse scripts)
* https://github.com/ernw/static-toolbox/releases/download/1.04/nmap-7.80SVN-x86_64-a36a34aa6-portable.zip - Linux
* https://github.com/andrew-d/static-binaries

### Cool resources
* https://www.blackhillsinfosec.com/the-rdp-through-ssh-encyclopedia/
