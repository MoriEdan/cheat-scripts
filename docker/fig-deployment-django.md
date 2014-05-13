Fig Django deployment cheats
===========================

<h4>Create Directory</h4>
<pre>
$ mkdir django
$ cd django
</pre>

<h4>Dockerfile</h4>
<pre>
$ nano Dockerfile
# add to the file:
FROM orchardup/python:2.7
RUN apt-get update -qq && apt-get install -y python-psycopg2
RUN mkdir /code
WORKDIR /code
ADD requirements.txt /code/
RUN pip install -r requirements.txt
ADD . /code/
</pre>

<h4>Requirements file</h4>
<pre>
$ nano requirements.txt
# add to the file:
Django
</pre>

<h4>Fig yml file</h4>
<pre>
$ nano fig.yml
# add to the file:
db:
  image: orchardup/postgresql
web:
  build: .
  command: python manage.py runserver 0.0.0.0:8000
  volumes:
    - .:/code
  ports:
    - "8000:8000"
  links:
    - db
</pre>

<h4>Build the project</h4>
<pre>
$ fig run web django-admin.py startproject django-project .
</pre>

<h4>Configure Database</h4>
<pre>
$ django-project
$ nano settings.py
# replace Databases section with:

DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql_psycopg2',
        'NAME': 'docker',
        'USER': 'docker',
        'PASSWORD': 'docker',
        'HOST': os.environ.get('DB_1_PORT_5432_TCP_ADDR'),
        'PORT': os.environ.get('DB_1_PORT_5432_TCP_PORT'),
    }
}

</pre>

<h4>Launch the App</h4>
<pre>
$ fig up -d   #run in background
$ fig run web python manage.py syncdb
</pre>

go to your_ip_address:8000
go to admin console your_ip_address:8000/admin

<h4>Check containers</h4>
<pre>
$ fig ps
$ docker ps
</pre>















