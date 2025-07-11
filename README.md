# Setup Drupal 11 on Codespaces

run <code>sh setup.sh</code>.

When it finishes run <code>cd drupal_site</code>.

Run <code>./vendor/bin/drush serve</code>.

Open the "ports" tab (right next to the terminal) and use the link under the "Local Address" to open your Drupal instance

admin login is

ACC: admin
PASS: 123

# if facing issues:
<code>sudo apt-get update
sudo apt-get install php-gd </code>

# check your php version
<code> php -v </code>

PHP 8.3.14

# add mission extension
<code> php --ini </code>

Configuration File (php.ini) Path: /usr/local/php/8.3.14/ini
Loaded Configuration File:         /usr/local/php/8.3.14/ini/php.ini
Scan for additional .ini files in: /usr/local/php/8.3.14/ini/conf.d
Additional .ini files parsed:      /usr/local/php/8.3.14/ini/conf.d/xdebug.ini


<code> find /usr -name gd.so </code>
/usr/lib/php/20230831/gd.so

<code> nano /usr/local/php/8.3.14/ini/php.ini </code>
either enable extension=gd
or
update to: extension=/usr/lib/php/20230831/gd.so



# Setup Local Development Environtment

add Twig.config to parameters on sites/develpment.service.yml
<code>
parameters:
  http.response.debug_cacheability_headers: true
  twig.config:
    debug: true
    auto_reload: true
    cache: false
</code>

copy example.settings.local.php into default directory and rename it to settings.local.php

Uncomment below code on settings.php
<code>
 if (file_exists($app_root . '/' . $site_path . '/settings.local.php')) {
   include $app_root . '/' . $site_path . '/settings.local.php';
 }
</code>