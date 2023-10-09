1. nmap IP and look for interesting ports/services
2. SMB/RPC -> read shares, mount shares
3. search for vulnerable versions

PrivEsc
1. sudo -l
2. SUID/GUID files
3. GTFO bin SUID/GUID execs
4. strings SUID/GUID execs
* PATH variable manipulation


### Wordlists
* `/usr/share/metasploit-framework/data/wordlists/unix_passwords.txt`
* `/usr/share/wordlists/seclists`
