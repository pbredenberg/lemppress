# LEMPDash
Version 0.0.3

LEMPDash is a command line tool to help streamline a [LEMP](https://lemp.io/) stack web hosting environment. Includes nginx server block and mysql database creation, backup, destruction, etc.

This tool is comprised of various shell scripts and ideas collected from around the web, arbitration given as neccessary.

## System Requirements
LEMPDash is written and tested on Ubuntu 14.04 so far, all other buyers, beware! Unless you have alot of free time.

### Recommended/Required Packages:
* nginx
* mysql-server
* php5-fpm
* php5-mysql

### Assumptions (for now)
* Nginx is located here: /etc/nginx
* You are cool with your server root(s) being here: /var/www/YOURSITE(S)/htdocs

## Installation
Get it:

```
git clone git@github.com:pbredenberg/lempdash.git
```

Install it:
```
cd lempdash
```
```
sudo ./install
```

## Upgrading
If there is a new version with shiny new features you'd like to use, you can do that without any funny business like checking for dependencies.

Assuming you still have, or have re-cloned (see Installation section) the LEMPDash repository, and have navigated into it on the command line:

```
sudo ./upgrade
```

## Usage
Lempdash is invoked thusly:
```
ldash
```

LEMPDash must be run as root when executing processes on the system level, for instance, when creating or removing nginx server blocks, or when backing up to folder owned by the root user.

As of version 0.0.3, you can: create, remove, or back up the following: nginx server blocks, site files, and MySQL databases with ease.

### cr (Create)
Create a site:
```
ldash cr site mysite.com
```

Create a database:
```
ldash cr db databasename databaseuser databasepassword
```

### rm (Remove)
Remove a site:
```
ldash rm site mysite.com
```

Remove a database:
```
ldash rm db databasename
```

Remove a database user:
```
ldash rm dbuser username
```

Note: Remove wants to do its' thing safely, so it will back up your site files and databases automatically when they are destroyed using zip, and place the backup in var/www/archive/YOURSITENAME.

### bu (Backup)
Back up a site:
```
ldash bu site mysite.com
```

Back up a database:
```
ldash bu db databasename
```

## Future Stuff
* Easily uninstall LEMPDash
* Better backup/archiving managment
* Server error summaries/reporting
* Server event notifications
* Setup options for system specific configurations
* Leverage WP-CLI to manage WordPress Sites
* Support MariaDB, MongoDB

