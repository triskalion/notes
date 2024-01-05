#### Port
- SMTP TCP: 25
#### nmap scripts
* `--script smtp-commands` - enumerate enabled verbs
* `--script smtp-enum-users` - enum users
* `nc/telnet <IP> <port>` - enumerate enabled verbs
    * `help` 
#### User enumeration - Verbs
__RCPT TO__
* `HELO <tester>.<localdomain>`
* `MAIL FROM <tester@tester.localdomain>`
* `RCPT TO <user@domain.com>` - where *user* is the name to be enumerated
__EXPN__
* `EXPN <user>`
__VRFY__
* `VRFY <user>`
#### User enumeration - Tools
* `smtp-user-enum` - https://pentestmonkey.net/tools/user-enumeration/smtp-user-enum
