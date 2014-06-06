Linux file management cheats
======================

<h4>Directory commands</h4>
<pre>
$ pwd      #returns current working directory
$ ls       #returns directory contents
$ ll       #same as ls -al, returns detailed list of contents
$ ls -al   #returns detailed list of directory contents

$ cp -R folder1 folder2   #recursively copy all contents from one folder to another
</pre>

<h4>File Commands</h4>
<pre>
$ diff file1 file 2    #compare two files
$ md5sum -t file    #compute hash
$ echo -n “string” | md5sum    #generate hash of string
$ sha1sum   #sha1 hash of file
$ find / -name string   #find string or file name
$ find -i -name file-name -type *.pdf   #find files of pdf type
</pre>

<h4>dd Commands</h4>
<pre>
$ dd if=/dev/hda of=disk.img conv=noerror,sync
$ dd skip =1000 count=2000 bs=8 if=file of=file   #cut blocks 1000 to 3000 from file
$ dd if=/dev/zero of=/dev/sda conv=noerror,sync   #write zeroes to an entire partition
$ dd if=/dev/urandom of=<file> bs=3145728    #create random 3mb file
$ dcfldd if=/dev/hda hash=md5,sha256 hashwindow=10G md5log=md5.txt sha256log=sha256.txt \
  hashconv=after bs=512 conv=noerror,sync split=10G splitformat=aa of=driveimage.dd  
  #images drive, calculates, stores hash
</pre>

<h4>Ownership</h4>
<pre>
$ sudo chown -R hduser:hadoop /usr/local/hadoop  #recursive ownership 
</pre>
