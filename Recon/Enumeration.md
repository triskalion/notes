### Linux
1. List all: `ls -la`
### Windows
1. List all: `dir /r`
2. Read secondary data streams - <span style="color:aqua">hm.txt:root.txt:$DATA</span>
	*  Powershell: `powershell (Get-Content *<primary-stream>* -Stream *<secondary-stream>*)`
	*  Regular cmd:	`more < *<primary-stream>*:*<secondary-stream>*:$DATA`
