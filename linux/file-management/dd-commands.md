dd command cheats
=================

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
