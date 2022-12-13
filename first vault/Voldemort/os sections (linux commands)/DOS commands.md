- cd
	- ![[Pasted image 20221213112346.png]]
- cd/
	- ![[Pasted image 20221213112407.png]]
	- no need for cap D
		- ![[Pasted image 20221213112417.png]]
- rd remove empty folder
	- rd /s = not empty
	- del deletes a file
- copy con fileName.txt
	- you write then ctrl z![[Pasted image 20221213112511.png]]
	- to print the content type fileName.txt
		- ![[Pasted image 20221213112604.png]]
- copy / cut then paste
	- `copy fileName.txt path` to make a `copy`
		- ![[Pasted image 20221213112641.png]]
	- `move fileName.txt path` to `cut`
		- ![[Pasted image 20221213112723.png]]
- F7 shows prev entered commands
- ren old new
- hide / unhide folders
	- ![[Pasted image 20221213112813.png]]
- version ver
	- ![[Pasted image 20221213112856.png]]
- to another partition
	- ![[Pasted image 20221213112931.png]]
	- we going back .. it remembers #i_need_help
	- to change a partition name `label`
		- ![[Pasted image 20221213114010.png]]
		- to format the partition D `format D:`
- how to run more than a command at once ?
	- use a batch .bat
		- ![[Pasted image 20221213114112.png]]
		- can be edited
		- the terminal may need input from you on running
	- the batch to print sys info then activate windows
		##### quaii tech
		`bcdedit -set TESTSIGNING OFF`
		the restart
		`shutdown /r`
		batch is
		`@echo off` 
		`systeminfo
		 `pause` 
		 `bcdedit -set TESTSIGNING OFF `
		 `shutdown /r``
