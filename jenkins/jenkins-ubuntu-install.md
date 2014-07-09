Jenkins CI Ubuntu install cheats
================================

<h4>Add Jenkins key, sources List and Install</h4>
<pre>
$ wget -q -O - http://pkg.jenkins-ci.org/debian/jenkins-ci.org.key | apt-key add -
$ echo deb http://pkg.jenkins-ci.org/debian binary/ > /etc/apt/sources.list.d/jenkins.list
$ apt-get update
$ apt-get install jenkins
</pre>
