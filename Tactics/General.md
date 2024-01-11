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

### Cool resources
* https://www.blackhillsinfosec.com/the-rdp-through-ssh-encyclopedia/
