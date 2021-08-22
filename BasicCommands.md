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

* ` echo `      displays thxt that we pass to it.

-------

### Working with files

* ` cat `       con**cat**enation – to display the content of the file on screen. 
  Use ` -n ` to display line numbers.

* ` tac `       (cat spelled backwards) print files in revrese. 

* ` less `      display the content of a file, one page at a time. <br/>
(space bar/f= goto next page, b=previous page, enter/down arrow=scroll by one line, / = search, q = quit)

* ` rev `       print the content of file by reversing the order of each line.  
* ` head `      prints first 10 lines of a file ( use -` -n 20 `  to display first 20 lines)
* ` tail `      prints last 10 lines of a file
* ` wc `        count of number of words, lines and bytes in file <br/>
( ` - l ` = line count, ` -w ` = word count,  ` -m ` = charactor count, ` -c ` = byte count)
* ` sort `      shows the sorted content of a file ( ` -u ` = unique values)

-------

### Redirecting & piping

* source content ` > ` destination location
* ` < `     pass the content of a file to standard input.
* ` 2> `    redirect the error log to a file
* ` &> `    redirect the standard output and error log to same file
  
* ` | `     pipe = connects a command to another command

| redirect | pipe |
| --- | --- |
| redirect connects a command to some file | pipe connects a command to another command |

* ` tr `    translate or delete characters from standard input, writing to standard output.

```console
pi@pi:~ $ echo name : 123 456 789
name : 123 456 789
pi@pi:~ $ echo name : 123 456 789 | tr -d [:alpha:]
 : 123 456 789
pi@pi:~ $ echo name : 123 456 789 | tr -d [:alpha:] | tr -d :
  123 456 789
pi@pi:~ $ echo name : 123 456 789 | tr -d [:alpha:] | tr -d : | tr -d [:blank:]
123456789
```

-------

#### TimeStamps 

* ` mtime `   modification time (inside of a file :time when the content of file last changed)
  when we type ` ls -l ` then by default, it shows mtime.

* ` ctime `   change time (outside of a file : ex. rename file, alter file, move file etc)
  when we type ` ls - lc ` then it shows change time. 
  when mtime changes, then ctime also changes. But opposite is not true.

* ` atime `   access time (updated when a file is read by application, ex. cat command)
*  when you type ` ls -lu ` then it shows last access time.
-------

### grep

* ` grep `      it searches files for specified words or patterns. (ex.grep 'one' filename.txt)
* ` grep -w `   match exact word (ex. grep -w 'number' filename.txt)
* ` grep -r `   recursive search which inclide all files under directory, sub-directory and their files etc.
 (Ex. grep -r 'hello' directoryName)
* ` grep -c `  count of searching word (ex. grep -c "i am" filename.txt )
-----

### other

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

* ` du -ha` disk usages ( -h for human readable format, -a for all)

* ` find ~ -type f -empty ` find all empty files from home folder

* ` find ~ -type f -empty -exec ls -l '{}' ';' ` find all empty files from home folder and also print the permissions for each folder.

* ` find -type f -name "*.txt" -exec cp '{}' '{}_copy' ';' `  find all files with extension txt. Then create copy of each file with suffix as copy.

* ` ip addr | grep inet ` check IP address of server
-------

### Permissions

* users : **u** = user, **g** = grpup, **o** = others, **a** = all  
* Permissions: **r** = read, **w** = write, **x** =execute
* Operators: 
  * **+** (add permission) 
  * **-** (remove permission) 
  * **=** (overrites any existing permission with the ones specified)
* Numeric permissions:
  * 4 = Read
  * 2 = Write
  * 1 = Execute

 ```console

r  |  w  |  x  
4  |  2  |  1  

rwx = 4 + 2 + 1 = 7
rw- = 4 + 2 + 0 = 6
r-x = 4 + 0 + 1 = 5
r-- = 4 + 0 + 0 = 4
-wx = 0 + 2 + 1 = 3
-w- = 0 + 2 + 0 = 2
--x = 0 + 0 + 1 = 1

Ex:
$> chmod 744 text.txt is same as

$> chmod u=rwx text.txt
$> chmod go=r text.txt

 ```  

* ` chmod `  to change permissions of user
* ` chmod o-r fineName.txt ` 



----
### Cron 
* allow you to schedule execute commands at perticular regular interval
* ` crontab -e ` editing the crontab
  
```console
Syntax:
a  b  c  d  e  command

a = Minutes (0 -59)
b = Hour  (0 - 23)
c = Day (1 - 31)
d = Month (1 - 12)
e = Day of week (0 - 6)

Cron characters:

* = any value
1-6 = Range of values (1 to 6)
1,6 = List of values (1 and 6)
*/2 = step values (every 2)

Ex:
30 * * * * command ( Run a job at 30 minutes in every hour)
0 0 * * * command ( Run a job every day at midnight )


```


----

### Regular Expressions (Regex)

* ` . `       match single charactor
* ` ^ `       match start of a line
* ` $ `       match end of a line
* ` [abc] `   match any charactor in the set
* ` [^abc] `  maych any charactor not in the set
* ` [A-Z] `   match charactor in a range
* ` * `       zero or more times 
* ` \ `       escape

----

### Keyboard shortcut for terminal:

* ` ctrl + l ` clear the screen

* ` ctrl + a ` & ` ctrl + e ` bring cursor to st**a**rt of line or **e**nd of line
* ` ctrl + f ` & ` ctrl + b ` move cursor **f**ront or **b**ack, one charactor at a time

* ` alt +  f ` & ` alt + e ` move cursor front or back, one word at a time
  
* ` ctrl + k ` remove text under the cursor location until the end of the line
* ` ctrl + u ` remove text under the cursor location until the start of the line

* ` alt + d ` to remove the text from current cursor location through end of word.
* ` ctrl + d ` to remove one charactor from current cursor location.

* ` alt + w ` to remove the text from current cursor location through start of word.

* ` ctrl + y ` to retrieve the most recently killed text.

* ` crtl + t ` to swap current charactor under the cursor with the one preceding it. 
* ` alt + t ` to swap current word under the cursor with the one preceding it. 
