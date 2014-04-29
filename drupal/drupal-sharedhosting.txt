Drupal shared host installation:

Download Drush:
$ git clone https://github.com/drush-ops/drush.git
$ chmod u+x drush

Install Composer:
$ cd ~
$ curl -sS https://getcomposer.org/installer | php
$ sed -i '1i export PATH="$HOME/.composer/vendor/bin:$PATH"' $HOME/.bashrc #changes Composers global bin directory
$ composer #should get manpage if its working

Install Drush dependencies:
$ cd drush
$ composer install


$ nano ~/.bashrc
add to the file:
alias drush='~/drush/drush'

$drush version #check if its working


Install Drupal:
$ cd ~/public_html
$ drush dl drupal
$ mv drupal-7.xx/* ~/public_html

go to /install.php #follow prompts


Increase PHP limits
$ cd ~/public_html
$ nano .user.ini
add to the file:
memory_limit = 512M
upload_max_filesize = 128M

go to: ?q=admin/reports/status to verify that the PHP version and memory is correct

Enable Clean Urls:
$ cd ~/public_html
$ nano .htaccess
add to the file:
RewriteEngine on
RewriteBase /
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_FILENAME} !-d
RewriteRule ^(.*)$ index.php?q=$1 [L,QSA]


Configuration Page loads slow or shows HTTP request error:
$ nano settings.php
add to the file:
$conf['drupal_http_request_fails'] = FALSE;

























