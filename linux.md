**File and directory Structure**

root folder :

bin: contains applications that can be used by other users
boot: necessary file for the start of the OS
dev: computer peripheral file are store on it
etc: configuration file
home: Personal document
lib: contains library who are share from application, .so files equivalent to .dll in windows
media: folder who are necessary when you want to go on a usb key or sd card
mnt: same as media but temporary
opt: directory use to stock add-ons
proc: information system file
root: Personal document of root
sbin: contains important system application
tmp: Temporary directory used by application to stock data
usr: contains application installed by user
var: contains file with variable file like logs

pwd :

To know where i am on the terminal
ex : pwd

which :

to know where is installed what you want
ex: which pwd

**Manipulation of file**

cat :

allow you to display the entire file
ex : cat text.txt

less :

Unlike cat, less display page per page the content
ex: cat text.txt
navigation :

space: display the rest of the content page per page
enter: display the rest of the content line by line
d: display half of the rest of the content
b: back from last scroll
y: back from one line
q: stop reading
=: indication on where you are on the file
h: help
/: to search a word | n: navigate to your search | N: navigate to your search but backwards

Head :

display the beginning of a file
cool trick :
-n :
display the number of line you wrote
ex: head -n 4 text.txt

Tail :

display the end of a file
cool trick :
-n :
display the number of line you wrote
ex: tail -n 4 text.txt

-f :
allow you to follow the end of a file like logs file
ex: tail -f text.txt
(to stop this ctrl + c)

**RDFM :**

navigation to the man :

To move on manual : PageUp PageDown / espace
To go to first page : Home
To go to last page : End
To search something : / + word | to travel around result : /
To quit : Quit

apropos :

it allow you to search everycommand who are about what you are looking for
ex : apropos sound

whatis :

it display a short description of the command
ex : whatis mkdir

**Search File :**

Locate :

easiest way to search a file, it will search on a database
ex : locate file.txt
**warning** if the document have been created less than 24 hours you will need to update the database of file with : sudo updatedb

Find :

Powerful command to search find and making other stuff, in contrary of Locate he will search on your hard drive
command description : find "where" "what" "what will you do" (only what is required)
basic ex: find -name "test.txt"
with location : find /var/ -name "syslog"
search by size : find -size +10M
by time, last time your modified it : find -name "_.odt" -atime 6
by type : find -name "syslog" -type f (can also write -type d for directory)
with "what will you do" : find -name "_.jog" -printf

**Extract, sort and filter data**

Grep :

command to search a word on file and display it
ex: grep text myfile | grep alias .bashrc
cool trick :
-i : not sensitivity case
-n : display line number
-v : invert the search, mean search line without the word you wrote.
-r : search in every file and directory | you have to precise the folder
ex : grep -r "i search something" test/
-e : regular expression to do more precise research

Sort :

command to sort content alphabetically
ex: sort fichier.txt

WC :

command to count word/line/caracter/size from a file
ex: wcnoms.txt

**Redirection flows**

> :

this arrow allow you to stock the result of a command line in a file
ex : cut -d , -f 1 notes.csv > eleves.txt

'>>' :

as the >, it allow you to stock the result of a command line in a file but it will not erase the file if the file already exist.
ex : cut -d , -f 1 notes.csv >> eleves.txt

2> :

redirect error in a file
ex: cut -d , -f 1 fichier_inexistant.csv > eleves.txt 2> erreurs.log
