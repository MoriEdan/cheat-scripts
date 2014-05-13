Fig Flask deployment cheats
===========================

<h4>Create Directory</h4>
<pre>
$ mkdir flask
$ cd flask
</pre>

<h4>Dockerfile</h4>
<pre>
$ nano Dockerfile
# add to the file:
FROM orchardup/python:2.7
ADD . /code
WORKDIR /code
RUN pip install -r requirements.txt
</pre>

<h4>Requirements file</h4>
<pre>
$ nano requirements.txt
# add to the file:
flask
redis
</pre>

<h4>Application File</h4>
<pre>
$ nano app.py
# add to the file:
from flask import Flask
from redis import Redis
import os
app = Flask(__name__)
redis = Redis(
    host=os.environ.get('REDIS_1_PORT_6379_TCP_ADDR'),
    port=int(os.environ.get('REDIS_1_PORT_6379_TCP_PORT'))
)

@app.route('/')
def hello():
    redis.incr('hits')
    return 'Hello World! I have been seen %s times.' % redis.get('hits')

if __name__ == "__main__":
    app.run(host="0.0.0.0", debug=True)
</pre>

<h4>Fig yml file</h4>
<pre>
$ nano fig.yml
# add to the file:
web:
  build: .
  command: python app.py
  ports:
   - "5000:5000"
  volumes:
   - .:/code
  links:
   - redis
redis:
  image: orchardup/redis
</pre>

<h4>Launch the App</h4>
<pre>
$ fig up -d   #run in background
$ fig run web python manage.py syncdb
</pre>

<h4>Open Port</h4>
<pre>
$ iptables -A INPUT -p tcp -m tcp --dport 5000 -j ACCEPT
</pre>

go to your_ip_address:5000

<h4>Check containers</h4>
<pre>
$ fig ps
$ docker ps
</pre>


