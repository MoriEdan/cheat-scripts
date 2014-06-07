Linux file commands cheats
==========================

<h4>Directory commands</h4>
<pre>
$ pwd      #returns current working directory
$ ls       #returns directory contents
$ ll       #same as ls -al, returns detailed list of contents
$ ls -al   #returns detailed list of directory contents

$ cp -R folder1 folder2   #recursively copy all contents from one folder to another
</pre>

<h4>File Ownership</h4>
<pre>
$ sudo chown -R hduser:hadoop /usr/local/hadoop  #recursive ownership 
</pre>


<h4>File Redirects</h4>
<pre>
$ cat file1 > newfile.txt  #cats the file to stdout and overwrites or creates new.txt
$ cat file1 >> newfile.txt  #cats teh file to stdout and appends or creates new.txt

$ ls ur8ueoidajfda 2> newfile.txt   #redirects the stderr to a new file or overwrites existing  
$ ls ur8ueoidajfda 2>> newfile.txt  #redirects the stderr to a new file or appends existing
$ ls ur8ueoidajfda 2>> /dev/null    #redirects stderr to dev null (nothingness)

$ cat file1.txt file2.txt > mystdoutput.txt 2> mystderror.txt 
#redirects the stdout to one file and the stderr to another
$ cat file1.txt file2.txt > mystdoutput.txt 2>&1
#redirects the stdout and stderr to the same file

</pre>

<h4>Cat</h4>
<pre>
$ set -o noclobber  #prevents overwriting of files
$ set +o noclobber  #turns of overwriting prevention 

$ cat file1 file 2   #concatenates two files into the stdout
$ cat file* | wc -l  #combines all files starting with 'file' and counts the number of lines
</pre>

<h4>Cut</h4>
<pre>
cut -f1 -d : /etc/passwd > output.txt   #cut field 1, use : as a delimiter and cretae or overwrite output.txt
</pre>

<h4>Diff</h4>
<pre>
$ diff file1 file2   #compares the lines of two files
</pre>

<h4>Split</h4>
<pre>
$ split -l 1 file1.txt   #splits each line into a seperate file (starting with xaa)
$ split -l 2 file1.txt   #splits every two lines into a seperate file (starting with xaa)
$ split -b 256 file1.txt  #splits every 256 byte chunks into seperate files
</pre>

<h4>Various Commands</h4>
<pre>
$ md5sum -t file    #compute hash
$ echo -n “string” | md5sum    #generate hash of string
$ sha1sum   #sha1 hash of file
$ find / -name string   #find string or file name
$ find -i -name file-name -type *.pdf   #find files of pdf type
</pre>

