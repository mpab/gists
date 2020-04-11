# Installation and setup

##remote connection

edit config settings

for community edition
/Library/LaunchDaemons/com.oracle.oss.mysql.mysqld.plist

for brew
/usr/local/Cellar/mysql/8.0.12/homebrew.mxcl.mysql.plist
(which is copied to: /Library/LaunchDaemons/homebrew.mxcl.mysql.plist on start)

```xml
  <array>
    <string>/usr/local/opt/mysql/bin/mysqld_safe</string>
    <string>--datadir=/usr/local/var/mysql</string>

    <!-- enable remote access -->
    <string>--bind-address=*</string>

    <!-- enable legacy authentication -->
    <string>--default_authentication_plugin=mysql_native_password</string>

    <!-- enable LOAD DATA LOCAL INFILE -->
    <string>--secure-file-priv=/Users/Shared/mysqlio</string>
  </array>
```

add remote user - MySQL shell

check account permissions

```console
$ select user, host FROM mysql.user WHERE User = 'eux';
$ create user eux IDENTIFIED BY '';
$ grant all ON *.* TO eux;
```

enable old password checks (for ODBC connection)

```console
$ alter user eux identified with mysql_native_password BY '';
```

enable user on all hosts (wildcard)

```console
$ update mysql.user set host='%' where user='eux';
```

propagate changes

```console
$ flush privileges;
```

## DATA IMPORT/EXPORT - disable file I/O restrictions

``` console
$ touch ~/.my.cnf
$ subl ~/.my.cnf
```

edit/insert

``` console
[mysqld]
secure_file_priv               = ''
```

above didn't work, try in plist file

``` xml
<string>--secure-file-priv=/Users/Shared/mysqlio</string>
```

### NOTE

Double check the above approach as is seems there is a "LOCAL" option which bypasses the restriction and allows import via the mysql client.
Update doesn't work - recommend use community edition

stop/start the daemon (plist name may be different)

``` console
sudo launchctl unload /Library/LaunchDaemons/com.oracle.oss.mysql.mysqld.plist

sudo launchctl load /Library/LaunchDaemons/com.oracle.oss.mysql.mysqld.plist
```

from a MySQL prompt

``` console
mysql> show variables like "secure_file_priv";
```

##General user management tips

https://www.cyberciti.biz/faq/how-to-delete-remove-user-account-in-mysql-mariadb/

##Homebrew

###Recommend don't use this, file load for tables is either broken or unreliable, these notes are for reference

```console
$ brew install mysql
```

https://stackoverflow.com/questions/9695362/macosx-homebrew-mysql-root-password

launchctl unload -w ~/Library/LaunchAgents/homebrew.mxcl.mysql.plist
rm -r /usr/local/var/mysql/
launchctl load -w ~/Library/LaunchAgents/homebrew.mxcl.mysql.plist
unset TMPDIR
mysql_install_db --verbose --user=`whoami` --basedir="$(brew --prefix mysql)" --datadir=/usr/local/var/mysql --tmpdir=/tmp

https://community.jaspersoft.com/wiki/uninstall-mysql-mac-os-x

```console
$ sudo rm /usr/local/mysql
$ sudo rm -rf /usr/local/mysql*
$ sudo rm -rf /Library/StartupItems/MySQLCOM
$ sudo rm -rf /Library/PreferencePanes/My*
$ rm -rf ~/Library/PreferencePanes/My*
$ sudo rm -rf /Library/Receipts/mysql*
$ sudo rm -rf /Library/Receipts/MySQL*
$ sudo rm -rf /private/var/db/receipts/*mysql*
```

"We've installed your MySQL database without a root password. To secure it run:
    mysql_secure_installation

MySQL is configured to only allow connections from localhost by default

To connect run:
    mysql -uroot

To have launchd start mysql now and restart at login:
  brew services start mysql
Or, if you don't want/need a background service you can just run:
  mysql.server start"

Don't do that!
check installation

brew services list

Fix bug in brew install

```console
$ sudo chown -R _mysql:mysql /usr/local/var/mysql
```

start service

```console
$ sudo brew services start mysql
```

connect locally

```connect
$ mysql -uroot
```
(exit)
