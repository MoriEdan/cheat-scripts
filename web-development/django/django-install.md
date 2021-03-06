Django installation cheats
==========================

<h4>Install dependencies:</h4>
<pre>
$ sudo curl -O https://bitbucket.org/pypa/setuptools/raw/bootstrap/ez_setup.py
$ sudo python ez_setup.py --user
$ sudo easy_install pip
</pre>


<h4>Install Django and modules:</h4>
<pre>
$ sudo pip install Django==1.6.1
$ sudo pip install dj-static #static file server
$ sudo pip install django-taggit #tagging module
</pre>


<h4>Create Django directory:</h4>
<pre>
$ mkdir site
$ cd site
$ sudo django-admin.py startproject blog
</pre>

<h4>Launch web server:</h4>
<pre>$ sudo chmod +x manage.py
$ sudo ./manage.py runserver
</pre>
go to localhost:8000

<h4>Sync Database:</h4>
<pre>
$ cd site/blog
$ sudo python ./manage.py syncdb #enter username and pwd
$ sudo chmod 755 dbsqlite3
$ sudo ./manage.py runserver 
</pre>
go to localhost:8000/admin to check if admin page working
login with credentials created with syncdb

<h4>Build Application directory:</h4>
<pre>$ sudo python manage.py startapp myblog</pre>



<h4>Configure static assets:</h4>
<pre>
$ cd site/blog/myblog
$ nano settings.py
# add the lines: 
STATIC_ROOT = 'staticfiles'
STATIC_URL = '/static/'

</pre>

<h4>Configure wsgi file for dj-static to serve files:</h4>
<pre>
$ cd site/blog/myblog
$ nano wsgi.py
# add the lines:
from dj_static import Cling
application = Cling(get_wsgi_application())
</pre>

<h4>Collect all static files and prepare for serving:</h4>
<pre>
$ cd site/blog
$ sudo python ./manage.py collectstatic
$ sudo python ./manage.py syncdb #make sure database is up to date
$ sudo python ./manage.py runserver #starts server; visit at localhost:8000/myblog
</pre>

