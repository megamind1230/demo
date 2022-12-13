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