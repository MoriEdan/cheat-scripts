Bash exit code script cheats
============================

<pre>
#! /bin/bash

mkdir test
error = $?

if [ $error -ne 0 ]; then
rm -r test
echo "removing folder"
mkdir test
ehcho "creating test folder"
touch test/newtext.txt
echo "creating new test folder"
echo "command completed"
exit 0

else 
    echo "command completed"

fi
</pre>
