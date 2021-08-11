### Basic Commands

* ` ls `        list the files/directories 
* ` ls -a `     list the files/directories including hidden files.
* ` ls –l `     list the files/directories in long format.
* ` ls –lh `    list the files/directories in long format. (h = human readable format of number)
* ` ls –l / `   list the files/directories in long format of root user.

* ` pwd `       present working directory
* ` whoami `    user name
* ` mkdir `     to make new directory.
* ` cd `        change directory
* ` cd .. `     change directory to parent (note there is a space between cd and .. )
* ` cd ~ `      change directory to home-directory
* ` clear `     clear the screen  (keyboard : ` ctrl + l ` )

* ` cp `        copy
* ` mv `        move or rename
* ` rm `        remove
* ` rm -Ri `    i= interactive
* ` rm -d `     remove empty directory
* ` rm -r `     remove directory
* ` rmdir `     remove empty directory
* ` cat `       concatenation – to display the content of the file on screen
* ` grep `      it searches files for specified words or patterns.
* ` histroy `  list of previously used commands
* ` histroy | less `  list of previously used commands with limit

* ` uname -s ` gives kernel name
* ` uname -o ` gives Operating System name
* ` uname -a ` gives all of the System information

* ` dmesg | less `      to show Linux boot messages
* ` cat/proc/cpuinfo `  to show processor infor, model name and cup architecture info.
* ` cat /proc/meminfo ` info. about memory installed

* ` man -s 1 -k remove ` ( from manual, section-1, find keyword for removing something)

* ` cat > textfile1 `   ( send screen input to file name textfile1)


### Keyboard shortcut for terminal:

* ` ctrl + l ` clear the screen

* ` ctrl + a ` & ` ctrl + e ` bring cursor to st*a*rt of line or *e*nd of line
* ` ctrl + f ` & ` ctrl + b ` move cursor *f*ront or *b*ack, one charactor at a time

* ` alt +  f ` & ` alt + e ` move cursor front or back, one word at a time

* ` crtl + t ` to swap current charactor under the cursor with the one preceding it. 
* ` alt + t ` to swap current word under the cursor with the one preceding it. 

* ` ctrl + k ` remove text under the cursor location until the end of the line
* ` ctrl + u ` remove text under the cursor location until the start of the line

* ` alt + d ` to remove the text from current cursor location through end of word.
* ` alt + w ` to remove the text from current cursor location through start of word.

* ` ctrl + y ` to retrieve the most recently killed text.