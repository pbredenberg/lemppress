# LEMPDash
LEMPDash is a collection of bash tools to aid the creation of nginx sites. Includes nginx server block and mysql database creation, backup, destruction, etc.

##System Requirements
LEMPDash is written and tested on Ubuntu 14.04 only, all other buyers, beware! Unless you have alot of free time.

###Recommended/Required Packages:
* nginx
* mysql-server
* php5-fpm
* php5-mysql

###Assumptions (for now)
* Nginx is here: /etc/nginx
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

## Usage
Lempdash is invoked thusly:
```
ldash
```

LEMPDash must be run as sudo when executing processes on the system level, for instance, when creating or removing nginx server blocks.

As of version (0.0.2), you can create or remove nginx server blocks, and MySQL databses/users.

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

Note: Remove wants to do its' thing safely, so it will back up your site files automatically using zip, and place the backup in var/www/archive/YOURSITENAME.

## Future Stuff

* Support MariaDB, MongoDB
* Backups for sites/DBs
* Uninstall script
* Setup options for system specific configurations

