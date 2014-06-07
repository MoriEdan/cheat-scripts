Grep commmand cheats
====================
<p>
Grep regexes:<br>
^:    begins with<br>
$:    ends with<br>
[ ] : character reference<br>
</p>

<p>
Grep exit codes:<br>
0: successfull<br>
1: no matches<br>
2: syntax errors<br>
</p>

<h4>Grep patterns</h4>
<pre>
$ grep ^hello test.txt   #finds all lines that begin with hello and prints to screen
$ grep -c ^hello test.txt  #finds all lines that begin with hello and prints the number to screen
$ grep hello& test.txt   #finds all lines that end with hello and prints them to screen

$ grep [e] test.txt   #matches every instance of the character e
$ grep [hel] test.txt   #matches every intance of all characeters h,e,l
$ grep ^[hel] test.txt  #matches every instance of characters h,e,l that begin each line
$ grep -i ^[hel] test.txt  #matches every instance of characters h,e,l that begin each line; case insensitive
$ grep [a-g] test.txt   #matches every instance of characters a-g
$ grep [1-9] test.txt   #matches every instance of numbers 1 thru 9

$ grep -f input.txt search.txt   #searches one file with the contents of another
$ grep -lr php /etc   #searches for all instances of php recursively in /etc
</pre>

<h4>egrep patterns</h4>
<pre>
egrep 'hello.*world' test.txt   #matches anything that has hello with world in the same line
egrep 'hello|world' test.txt  #matches any line with hello or world
egrep -v 'hello|world' test.txt  #does not match any line with hello or world 
egrep 'hello|world' test.txt | grep -v user_name   #matches any line with hello or world but not user_name
</pre>
