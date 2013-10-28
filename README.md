# vagrant-slitaz

Vagrant setup based on Slitaz Linux. Started from base cooking image 8Mb.
Built against Virtual Box Guest Addins v4.3.

## Benefits
The main one is the small vagrant's box size ~105Mb. Despite this the Slitaz guest is equipped with:
Apache2.4, php-5.4.13, xdebug-2.2.3, perl-5.12.3, MySql-5.5.27, sqlite3, php-cli, git-1.8.3, composer-2013-10-21, 
ngrok, phpMyAdmin-3.5.2, openssh-5.9

Installed php extensions:
- gd.so
- mysql.so
- openssl.so
- mysqli.so
- pdo_mysql.so
- mcrypt.so
- xdebug.so

## Getting Started

- Install VirtualBox v4.3([Download](https://www.virtualbox.org/wiki/Downloads))
- Install Vagrant >= v1.35 ([Download](http://downloads.vagrantup.com/))

## Usage

- Clone a copy of this repository to your local system or download it zipped.
- Navigate to main directory (where Vagrantfile resides) with your terminal and run `vagrant up`.

After all you should be able to visit [http://localhost:8888](http://localhost:8888)

## Example Usage with Laravel
After `vagrant up` and `vagrant ssh`, go to `/projects/www` directory.
Then type following command to create Laravel based project named "test":
`composer create-project laravel/laravel test --prefer-dist`
The 'test' directory will appear under /project/www. Now you can load a project into you preffered IDE
using synched 'test' folder from the host side.

Web app can be accessed by [http://localhost:8888/test/public](http://localhost:8888/test/public)

Additional functionallity could be added using `vagrant ssh` into guest OS.

Enjoy!


