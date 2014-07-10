Selenium Python test cheats
===========================


<h4>Basic Python test</h4>
<pre>
$ mkdir tests && cd tests
$ nano sel_test.py

# add to the file
from selenium import webdriver

browser = webdriver.Firefox()
browser.get('http://google.com')

assert 'Google' in browser.title, "Browser title was '%s'" % browser.title


<h4>Run test</h4>
<pre>
$ python sel_test.py
# if fails, will print to screen
# if successfull no output
</pre>

<h4>Kill firefox processes from tests</h4>
<pre>
$ killall firefox
</pre>
