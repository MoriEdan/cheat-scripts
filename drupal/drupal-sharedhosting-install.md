Drupal shared host installation:
===============================

<h4>Download Drush:</h4>
<pre>
$ git clone https://github.com/drush-ops/drush.git
$ chmod u+x drush
</pre>


<h4>Install Composer:</h4>
<pre>
$ cd ~
$ curl -sS https://getcomposer.org/installer | php
$ sed -i '1i export PATH="$HOME/.composer/vendor/bin:$PATH"' $HOME/.bashrc #changes Composers global bin directory
$ composer #should get manpage if its working
</pre>


<h4>Install Drush dependencies:</h4>
<pre>
$ cd drush
$ composer install
$ nano ~/.bashrc
# add to the file:
alias drush='~/drush/drush'

$drush version  #check if its working
</pre>


<h4>Install Drupal:</h4>
<pre>
$ cd ~/public_html
$ drush dl drupal
$ mv drupal-7.xx/* ~/public_html
</pre>

go to /install.php #follow prompts


<h4>Increase PHP limits</h4>
<pre>
$ cd ~/public_html
$ nano .user.ini
# add to the file:
memory_limit = 512M
upload_max_filesize = 128M
</pre>

go to: ?q=admin/reports/status to verify that the PHP version and memory is correct


<h4>Enable Clean Urls:</h4>
<pre>
$ cd ~/public_html
$ nano .htaccess
# add to the file:
RewriteEngine on
RewriteBase /
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_FILENAME} !-d
RewriteRule ^(.*)$ index.php?q=$1 [L,QSA]
</pre>

<h4>Configuration Page loads slow or shows HTTP request error:</h4>
<pre>
$ nano settings.php
# add to the file:
$conf['drupal_http_request_fails'] = FALSE;
</pre>
























