# drupal

run sh setup.sh

```sudo apt-get update
sudo apt-get install php-gd ```

# check your php version
``` php -v ```
PHP 8.3.14

# add mission extension
``` php --ini ```

Configuration File (php.ini) Path: /usr/local/php/8.3.14/ini
Loaded Configuration File:         /usr/local/php/8.3.14/ini/php.ini
Scan for additional .ini files in: /usr/local/php/8.3.14/ini/conf.d
Additional .ini files parsed:      /usr/local/php/8.3.14/ini/conf.d/xdebug.ini


``` find /usr -name gd.so ```
/usr/lib/php/20230831/gd.so

``` nano /usr/local/php/8.3.14/ini/php.ini ```
either enable extension=gd
or
update to: extension=/usr/lib/php/20230831/gd.so