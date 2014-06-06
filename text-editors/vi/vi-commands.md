Vi cheats
=========


<h4>Vi commands</h4>
<pre>
i      #insert mode
esc    #leave insert mode
esc shift   #enter into : mode


yy   #executes a yank and creates a copy buffer
7yy  #copies the first 7 lines into a buffer
p    #pastes the line from buffer on a new line
P    #pastes the line from buffer into line above cursor
o    #adds a line after the cursor
u    #undo last edit

R    #replaces or writes over text
dd   #deletes one line at a time at position of cursor
3dd  #deletes three lines after cursor
cc   #overwrites an entire line of code at cursor
cw   #overwrites one word at cursor

/test    #searches top down for the keyword 'test'
?test    #searches bottom up for keyword 'test'
shift n  #goes to the instance above the keyword
n        #goes to the instance below the keyword


h         #left cursor move
l         #right cursor move
j         #down cursor move
k         #up  cursor move
gg        #send cursor to top of file
shift h   #sends cursor to top of file
shift gg  #send cursor to end of file
shift l   #sends cursor to the end of file



:=    #prints out number of lines in file
:wq   #save and quite vi
:w    #save without quitting
:q!   #quite without saving


</pre>

