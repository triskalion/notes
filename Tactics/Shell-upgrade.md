* `python -c 'import pty;pty.spawn("/bin/sh")'` - spawn interactive shell
    * Press Ctrl-z to background the current shell, then on your terminal type:
	* stty raw -echo; fg <enter><enter>
	* stty rows 16 columns 136
* `python3 -c "import pty;pty.spawn('/bin/bash')"`

