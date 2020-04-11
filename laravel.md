# Loads of stuff

## TODO: change the DB stuff, add info about creating DB using scripts

Firstly - if you need to reset the vagrant container

```console
~/$ vagrant destroy
```

mysql database issues...

.env and database.php have different settings
to harmonise for both vagrant and local servers

If you need to add another schema or user - edit the following files and change the user, password and schema. But remember that this won't create the schema or user.

$APP/.env

``` PHP
DB_HOST=127.0.0.1
DB_DATABASE=homestead
DB_USERNAME=homestead
DB_PASSWORD=
```

$APP/config/database.php

``` PHP
database.php
'mysql' => [
            'driver'    => 'mysql',
            'host'      => env('DB_HOST', '127.0.0.1'),
            'database'  => env('DB_DATABASE', 'homestead'),
            'username'  => env('DB_USERNAME', 'homestead'),
            'password'  => env('DB_PASSWORD', 'secret'),
            'charset'   => 'utf8',
            'collation' => 'utf8_unicode_ci',
            'prefix'    => '',
            'strict'    => false,
            'engine'    => null,
        ],
```

start the application host server:

vagrant
$ vagrant up

local test
$ php artisan serve --port=8080

ensure the DB user is created before running the scripts

``` console
~/Homestead$ php artisan migrate
```

---

Hosting multiple sites

Set mappings inside Homestead.yaml

``` yaml
folders:
    - map: ~/Projects
      to: /home/vagrant/projects

sites:
    - map: todo.app
      to: /home/vagrant/projects/todo.app/public
    - map: emil.app
      to: /home/vagrant/projects/emil.app/public
    - map: fluent.app
      to: /home/vagrant/projects/fluent.app/public
    - map: homestead.app
      to: /home/vagrant/projects/homestead.app/public
```

edit /etc/hosts

``` bash
192.168.10.10   todo.app
192.168.10.10   emil.app
192.168.10.10   fluent.app
192.168.10.10   homestead.app
```

(re) provision vagrant (only if sites has changed)

``` console
~/Homestead$ up --provision
```
