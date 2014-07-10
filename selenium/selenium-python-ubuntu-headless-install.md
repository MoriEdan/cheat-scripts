Selenium Ubuntu install cheats
==============================

<h4>Intsall Pip</h4>
<pre>
$ apt-get install python-pip -y
</pre>

<h4>Intsall Selenium</h4>
<pre>
$ pip install --upgrade selenium
</pre>

<h4>Intsall Firefox</h4>
<pre>
$ apt-get install firefox
</pre>

<h4>Install and configure X Virtual Framebuffer</h4>
<pre>
$ apt-get install xvfb
$ Xvfb :1 -screen 0 800x600x24 > /dev/null 2>&1 &
$ export DISPLAY=:1
</pre>
