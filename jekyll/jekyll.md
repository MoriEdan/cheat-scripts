Jekyll cheats
=============

<h3>Load Ruby version in RVM:</h3>
<pre>
$ rvm use 2.1.0
$ gem install jekyll
</pre>

<h3>Configure yaml file:</h3>
<pre>
$ nano _config.yml

add the following:
name: site name
markdown: redcarpet

</pre>

<h3>File Structure setup:</h3>
<pre>
$ mkdir _includes #headers and footers
$ mkdir _layouts #used in themes
$ mkdir _posts
</pre>

<h3>Download Bootstrap:</h3>
<pre>
$ git clone https://github.com/twbs/bootstrap.git
# move bootstrap-theme.css, bootstrap-theme.min.css, bootstrap.css, bootstrap.min.css to the /css folder
</pre>

<h3>Download Icons:</h3>
<pre>
$ git clone https://github.com/FortAwesome/Font-Awesome.git #Font Awesome
$ git clone https://github.com/aristath/elusive-iconfont.git #elusive
$ git clone https://github.com/Keyamoon/IcoMoon--limited-.git #icomoon
# move buttons folders to the /css folder
</pre>

<h3>Enable Bootstrap & Jquery js files:</h3>
<pre>
$ nano _layouts/default.html
add to the file:
<script src="{{ site.url }}/js/bootstrap.js"></script>
<script src="http://code.jquery.com/jquery-1.10.1.min.js"></script>
</pre>

<h3>Enable Bootstrap & Font Awesome CSS files:</h3>
<pre>
$ nano _includes/header.html
add to the file:
<link rel="stylesheet" href="{{ site.url }}/css/bootstrap.css">
<link href="//netdna.bootstrapcdn.com/font-awesome/4.0.3/css/font-awesome.css" rel="stylesheet">
</pre>

<h3>Generate site:</h3>
<pre>
$ jekyll build #generates sites at ./_site
</pre>

<h3>Serve to Localhost:</h3>
<pre>
$ jekyll serve #serves to localhost:4000
or
$ jekyll serve --watch #serves to localhost:4000 and regenerates for changes
</pre>

<h3>If localhost:4000 socket stays open:</h3>
<pre>
$ sudo lsof -wni tcp:4000 #mark down what pid is using the socket
$ sudo kill -9 <pid>
</pre>
