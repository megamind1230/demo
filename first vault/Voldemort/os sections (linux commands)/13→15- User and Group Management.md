- whoami
	- gives the username
- id
	- ![[Pasted image 20221213122144.png]]
- ![[Pasted image 20221213122211.png]]
- 7 cols → username : password : userId : primary group id : description : name of the home directory :
- types of users
	- root / superuser 0
	- service 1:999
	- normal 1000 : bigger
- sudo
	- نفذ الأمر كرووت
- sudo useradd -m UserName
- sudo passwd UserName
- sudo usermod -c “desc” UsreName
	- to change the description col of UsreName
- sudo usermod -l newName UsreName
	- change user name
- لو عايز تتأكد هتعرض آخر سطر في الفايل دا
	- ![[Pasted image 20221213122427.png]]
- sudo usermod -s where_to_put_new_user_login_shell UserName
	- sudo usermod -s /bin/bash UserName
		- الأول ايه هي الشل
			- ![[Pasted image 20221213122457.png]]
- sudo su WhoToSwitchTo
	- switch user
- sudo userdel -r UsreName


- ---

- علشان تعرض كل الجروبس
- ![[Pasted image 20221213122628.png]]
- sudo groupadd GroupName
	- without password
- sudo groupadd -g ID -p PW GroupName
	- with id and password
- sudo groupmod -n newName GroupName
	- تغير اسم المجموعة
- sudo goupdel GroupName

- ---

- ADD USER TO GROUP
- simple ( just add a previously created one to a group)
	- ![[Pasted image 20221213122737.png]]
	- عايز تتأكد id UserNameWanted
	- ![[Pasted image 20221213122803.png]]
- (create a new user + determine shell + add to group in one command )
	- ![[Pasted image 20221213122829.png]]
