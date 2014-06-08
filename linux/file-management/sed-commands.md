Sed commands cheats
===================

<p>
[ ] : character class
^   : used inside of character class means that it does not include 
*   : means anything can match except whats in the character class

<h4>Sed commands</h4>
<pre>
$ sed 's/oldstring/newstring/' test.txt   #replaces first instance of oldstring with newstring
$ sed 's/oldstring/newstring/g' test.txt  #replaces all instances of oldstring with newstring
$ sed 's/oldstring/newstring/w new.txt' test.txt   #writes the replacements to a new file

$ sed 's/oldstring/w new.txt' test.txt   #searches for oldstring and writes that to a file
$ sed '0,/oldstring/s/newstring/' newtest.txt   #searches for the 0th (1st) intance of oldstring and replaces it

$ sed 's/&lt[^&gt]*&gt//' test.txt
# finds pattern starting with '<' as long as it isnt followed by '>'
# can have anything in between '<' and '>'
# removes the pattern from stdout
</pre>
