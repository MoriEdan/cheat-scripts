Sleuthkit cheats
================

<h4>Install:</h4>
<pre>
$ apt-get install sleuthkit
</pre>

<h4>Commands:</h4>
<pre>
$ mmls -a image-name	#allocated partitions no meta partitions
$ fls -l		#lists long info including MAC times
$ fls device-name meta-data-address 	#finds sub-directories
$ icat image name metadata address	#lists raw bytes of inode
$ ifind -d block-number image-file		#finds metadata address of a block on disk
$ istat image-name metadata-address		#lists all metadata about a file or directory
$ blkcat image-name block-number		#lists all of the contents of a block
$ blkls -a image-name start-block-stop-block	#find block number of a file for allocated blocks only
$ blckcat image-name block-number 	#reads the contents of the block to the screen
</pre>


<h4>Common workflow:</h4>
run fls to get the metadata address of the file<br>
run istat on the metadata address<br>
istat will list the block numbers of the file<br>
use blkcat to read the blocks<br>
if a file is non fragmented the number of blocks options can be used to read the entire file<br>
