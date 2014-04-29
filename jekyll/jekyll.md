Jekyll cheats
=============

<h3>Load Ruby version in RVM:</h3>
{% highlight bash %}
$ rvm use 2.1.0
$ gem install jekyll
{% endhighlight %}


<h3>Configure yaml file:</h3>
{% highlight bash %}
$ nano _config.yml

add the following:
name: site name
markdown: redcarpet
{% endhighlight %}


<h3>File Structure setup:</h3>
{% highlight bash %}
$ mkdir _includes #headers and footers
$ mkdir _layouts #used in themes
$ mkdir _posts
{% endhighlight %}


<h3>Download Bootstrap:</h3>
{% highlight bash %}
$ git clone https://github.com/twbs/bootstrap.git
# move bootstrap-theme.css, bootstrap-theme.min.css, bootstrap.css, bootstrap.min.css to the /css folder
{% endhighlight %}


<h3>Download Icons:</h3>
{% highlight bash %}
$ git clone https://github.com/FortAwesome/Font-Awesome.git #Font Awesome
$ git clone https://github.com/aristath/elusive-iconfont.git #elusive
$ git clone https://github.com/Keyamoon/IcoMoon--limited-.git #icomoon
# move buttons folders to the /css folder
{% endhighlight %}


<h3>Enable Bootstrap & Jquery js files:</h3>
{% highlight bash %}
$ nano _layouts/default.html
add to the file:
<script src="{{ site.url }}/js/bootstrap.js"></script>
<script src="http://code.jquery.com/jquery-1.10.1.min.js"></script>
{% endhighlight %}


<h3>Enable Bootstrap & Font Awesome CSS files:</h3>
{% highlight bash %}
$ nano _includes/header.html
add to the file:
<link rel="stylesheet" href="{{ site.url }}/css/bootstrap.css">
<link href="//netdna.bootstrapcdn.com/font-awesome/4.0.3/css/font-awesome.css" rel="stylesheet">
{% endhighlight %}


<h3>Generate site:</h3>
{% highlight bash %}
$ jekyll build #generates sites at ./_site
{% endhighlight %}


<h3>Serve to Localhost:</h3>
{% highlight bash %}
$ jekyll serve #serves to localhost:4000
or
$ jekyll serve --watch #serves to localhost:4000 and regenerates for changes
{% endhighlight %}


<h3>If localhost:4000 socket stays open:</h3>
{% highlight bash %}
$ sudo lsof -wni tcp:4000 #mark down what pid is using the socket
$ sudo kill -9 <pid>
{% endhighlight %}

