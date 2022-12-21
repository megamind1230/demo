## DOS
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


---


## Working with Directories part 1,2

- pwd
	- working directory
	- `~` home dir symbol
	- Cap D required![[Pasted image 20221213114735.png]]
-  cd
	- cd / is to go to root
	- cd ~ go to home dir
	- cd - go to the previously used dir (not on Windows)
	- cd .. go back one step
- ls list some of the contents of a dir
	- ls -a hidden are shown also
	- ls -l for long shows what’s not hidden .. with some more details{ these details are intelligible for an expert }
	- ls -hl human-readable ling .. like -l .. but intelligible for almost everyone .. same as -lh
	- can list anything form anywhere
		- ![[Pasted image 20221213114948.png]]
	- can list more than a dir
		- ![[Pasted image 20221213115008.png]]

---

## 4- Working with Directories part 3

- mkdir
	- making dirs on root is denied
	- make a dir inside another dir .. in the current place I’m in
		- ![[Pasted image 20221213115119.png]]
	- make a dir inside another dir .. while I’m in a way far place
		- you must use a path
			- ![[Pasted image 20221213115148.png]]
	- to make a hierarchy at once use -p
		- ![[Pasted image 20221213115225.png]]
- rmdir
	- rmdir -p
		- ![[Pasted image 20221213115314.png]]
- can do more than one command at a line using ;
	- ![[Pasted image 20221213115349.png]]




---


## 6,7- Working with Files part 1


- file
	- لمعرفة نوع الفايل
- touch
	- لعمل فايلات
	- touch -t {time stamp} nameOfFile بيحدد معاد انشاءه زي المكتوب
		- ممكن تتأكد عن طريق ال ls -l
		- time stamp = 202012040817→ 2020-12-04 08:17 → yyyy-mm-dd hh:mm
- rm
	- لحذف فايل مش فولدر
	- rmdir لحذف فولدر فاضي
	- rm -rf  لحذف فولدر مش فاضي
	- recursion force
- cp
	- فايلين
		- ![[Pasted image 20221213115933.png]]
	- فولدرين
		- ممكن تلزمك -r
	- فايل مع فولدر
		- cp file folder هياخد منه نسخة بس
	- `cp whatever .` يعني اعمل نسخة في نفس المكان اللي انا فيه
- mv
	- لعمل ريمنيم
	- لعمل موف مع كت
- rename
	- ![[Pasted image 20221213120128.png]]
	- rename 's/file/newfile/' *.txt
		- خلي كل الفايلات التكست واللي في اسمها فايل تتحول إلى نيوفايل
	- rename 's/\.png/\.gif/' *.png
		- امسك كل الفايلات البنج استبدل أي امتداد بنج بواحد جف
- wget
	- حط بعدها لنك صورة او بي دي اف هيتحمل
- ![[Pasted image 20221213120224.png]]



---


## 9,10- Working with file contents part 1

- head
	- بيعرض اول 10 سطور في الفايل
	- head -16 fileName 
		- كده يعرض اول16
	- head -c4 fileName
		- اعرض اول 4 حروف / بايتس
- tail عكسها
- cat
	- يعرض الفايل كامل بالترتيب
	- `cat file1 file2 > somefile`
		- هيحقن المحتويين في فايل واحد من غير ما يعرض 
	- `cat > somefile`
		- هيعمل لك فايل ويخيلك تكتب فيه.. ولما تخلص اعمل ctrl d
	- `cat > somefile<<hellNah`
		- هيفضل يستقبل لحد ما يقابل hellNah
- tac يعرض أسطر الفايل بالعكس
- more
	- بيعرض المحتوي مجزأ .. دوس انتر لعرض جزئية بسيطة أخرى.. دوس مسافة هيعرض جزئية اكبر
- less
	- زي اللي فوقها بس.. لما توصل للنهاية اعمل ctrl z
- strings
	- cat بتعرض أي حاجة سواء كانت مقروءة او غير
	- strings بتعرض المقروء وفقط
		- ![[Pasted image 20221213121441.png]]
- sort
	- ترتيب تصاعدي
	- sort -r ترتيب تنازلي
- wc
	- بتعمل تقرير برقم الأسطر والكلمات والحروف
	- 
- stat
	- معلومات عن الفايل
- grep
	- grep somestr fileName
- nano
```text
ctrl k > cut

ctrl u > paste

ctrl o > save

ctrl x > exit

ctrl / or ctrl w ctrl t> go to line

nano -v somefile > view only mode

`nano +numb somefile` go to the specific line in file

alt u / alt e > undo / redo

ctrl t ctrl s > check spelling

ctrl a / e > home of line / end

alt a then move > like mouse selection

ctrl j > show wrapped line
```

#vim #nano 


---

## 12- Man Pages

- whatis
	- whatis commnad > هيعرض وظيفة الكوماند
	- رقم 1 يعني تبع المستخدمين العاديين 8 يعني رووت
- man
	- تفاصيل أكتر من whatis
	- للخروج q
- info
	- تفاصيل اكتر من man
- whereis
	- ![[Pasted image 20221213122024.png]]
- which
	- ![[Pasted image 20221213122041.png]]

#still_os

---


## 13→15- User and Group Management

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




---


## vim

vim is a modal editor, having many modes 
type `vimtutor` as a command to learn more than mentioned
- ## normal mode
	- the mode used just for copy - paste - search - navigate and not adding text
	- j = down
		- k = up
	- l = right
		- h = left
	- or use the arrows
	- gg = go to 1st line
		- shift g = go to last line
			- 5 shift g = go to 5th line 
	- 5 any of hjkl = moves that number towards (==you can combine numbers with keybindings to repeat them==)
	- 0 = go to the start of line 
		- $ = go to the end on line
	- dd = delete line
	- p = paste
	- u times = undo
	- /anyword = search
		- enter = ready to edit 1st instance
		- n = next found
		- shift n = previous one
	- hwo to exit vim ?
		- :q = if no changes done
		- :q! = if there are + don't want to save them
		- :wq = if want to save them
- ## insert mode
	- 6 ways to enter it
		- i = starting right before the char you're on
			- shift i = starting at the start of line
		- a = for append , starting right before the char you're on
			- shift a = starting at the end of line
		- o = create new line below
			- shift o = create new line above
	- esc = back to normal mode
- ## command mode
	- learn some & the #reg_exp
	- #attractive ?
		- to save these config & not lose them >> put them in the vim config file
			- there ![[Pasted image 20221213103916.png]]
		- :set number = show line numbers
			- :set relativenumber = along with number to better for vim
		- :set mouse=a = mouse activated
		- :set tabstop=4 
			- :set shiftwidth=4 
			- :colorscheme anyname
			- :set autoindent
- ## visual mode
	- shift v  move to select a block then do > d > move to anyplace > d = moved a block





#vim #vi #test_editor #quick #productivity #dev