### Linux
1. List all: `ls -la`
### Windows
1. List all: `dir /r`
2. Read secondary data streams - **hm.txt:root.txt:$DATA**
	*  Powershell: `powershell (Get-Content *<primary-stream>* -Stream <secondary-stream>)`
	*  Regular cmd:	`more < <primary-stream>:<secondary-stream>:$DATA`
