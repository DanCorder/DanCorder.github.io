---
layout: blog
title: "Installing Drupal on a Mac"
---

The Drupal site contains full instructions for both [prerequisites](http://drupal.org/requirements) and [installation](http://www.blogger.com/) but somethings were not immediately clear to me and some of the documentation is fairly long so I thought I'd distill them here.

Install Apache - On a Mac you don't need to do this as it's already there, you just need to [enable it](http://macdevcenter.com/pub/a/mac/2001/12/07/apache.html) in System preferences under Sharing -> Web Sharing.

Install [MySql](http://www.mysql.com/downloads/mysql/) - You get the option of 32 bit or 64 bit installs. It seems that at the moment it's still [safer to install the 32 bit version](http://stackoverflow.com/questions/1436422/better-to-install-mysql-32bit-or-64bit-on-my-64bit-intel-based-mac-perl-python-u). I downloaded the dmg version and installed both packages (so MySql will start up automatically with the machine) and the preferences panel.

Install PHP - Again this is already installed on your Mac you just need to [activate it](http://stackoverflow.com/questions/1293484/easiest-way-to-activate-php-and-mysql-on-mac-os-10-6-snow-leopard).

Download Drupal and unzip it somewhere, (the Drupal instructions will link it to Apache later on).

Configure MySql (by default installed to /usr/local/mysql/bin). The following step by step instructions assume that MySql has only just been installed and has not been configured at all yet.

Log in as root:

`mysql -u root`

Then the following sets up a root user password:

`SET PASSWORD FOR 'root'@'localhost' = PASSWORD('secret_password');`

Create a user for use by Drupal

`CREATE USER 'drupal'@'localhost' IDENTIFIED BY 'another_password';`

Create a database for use by Drupal

`CREATE DATABASE drupalDb;`

Allow the Drupal user to manipulate the Drupal database (note the ` characters that are not \')
```
GRANT SELECT, INSERT, UPDATE, DELETE, CREATE, DROP, INDEX, ALTER, LOCK TABLES, CREATE TEMPORARY TABLES ON `drupalDb`.* TO 'drupal'@'localhost';
FLUSH PRIVILEGES;
```

Quit MySql

`\q`

Follow the [remaining installation instructions](http://drupal.org/node/540242) on the Drupal site.

The Mac specific instructions on the Drupal site are a bit mangled. This page explains how to set up virtual hosts more clearly:

http://drupal.org/node/238805

One important note here is that if you put your Drupal files somewhere non-standard then you could end up getting 403 errors. [This page](http://www.noah.org/wiki/Apache2_VirtualHost_403_error) has some suggestions on how to fix things. Personally I just put the Drupal files in a subdirectory of /Library/WebServer/Documents.

Once that's all done you ought to be able to go to the virtual site you set up and see the drupal installation start page. From there it ought to be plain sailing.

But in my case it wasn't. A final couple of useful points:
- You'll probably get an error about the files directory. Just create the directory manually and give the _www group write access to it.
- If you're installing on Snow Leopard you'll probably get an error after entering the database details. To get around this, click on advanced options and change the host name from localhost to 127.0.0.1. 