# LEMPDash
Version 0.0.4

LEMPDash is a command line tool to help streamline a [LEMP](https://lemp.io/) stack web hosting environment. Includes nginx server block and mysql/mariadb database creation, backup, destruction, etc.

This tool is comprised of various shell scripts and ideas collected from around the web, arbitration given as neccessary.

## System Requirements
LEMPDash is written and tested on Ubuntu 14.04 so far, all other buyers, beware! Unless you have alot of free time.

### Recommended/Required Packages:
* nginx
* mysql-server/mariadb-server
* php5-fpmldash
* php5-mysql

### Assumptions (for now)
* Nginx is located here: /etc/nginx
* You are cool with your server root(s) being here: /var/www/YOURSITE(S)/htdocs

## Installation
Get it:

```
git clone https://github.com/pbredenberg/lempdash.git
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

## Uninstalling
I knew you'd hate this. Enjoy the bitter end...

```
sudo ./uninstall
```

## Usage
Lempdash is invoked thusly:
```
ldash
```

LEMPDash must be run as **root (sudo)** when executing processes on the system level, for instance, when creating or removing nginx server blocks, or when backing up to folder owned by the root user.

On some servers, you may not need to do this depending on your particular permissions, or if you are logged in directly as root.

**To be totally clear for those less experienced, you usually have to run LEMPDash like this:**

```
sudo ldash
```

As of version 0.0.3, you can: create, remove, or back up the following: nginx server blocks, site files, and MySQL databases with ease.

### cr (Create)
**Create a site:**
```
ldash cr site mysite.com
```
LEMPDash will ask you to specify a user and a group. This should match whomever the user is whom owns/runs your webserver. Say no to leave the defaults.

**Tip:** *The default for this setting is the owner of the /var/www directory. If your nginx user for all your sites is the same, make sure the desired user and group own the /var/www directory.* 

**Create a database:**
```
ldash cr db databasename databaseuser databasepassword
```

### rm (Remove)
**Remove a site:**
```
ldash rm site mysite.com
```

**Remove a database:**
```
ldash rm db databasename
```

**Remove a database user:**
```
ldash rm dbuser username
```

**Note:** *Remove wants to do its' thing safely, so before destroying anything, it will back up your site files and databases automatically using zip, and place the backup in var/www/archive/YOURSITENAME.*

### bu (Backup)
**Back up a site:**
```
ldash bu site mysite.com
```

**Back up a database:**
```
ldash bu db databasename
```

### ls (List)
**List all sites:**
```
ldash ls site
```

**List all databases:**
```
ldash ls db
```

**List all backups:**
```
ldash ls bu
```

### rd (Redirect)
**Redirect one site to another site:**
```
ldash rd site OriginalSite.com SiteToPointTo.com
```

## Future Stuff
* Better backup/archiving managment
* Server error summaries/reporting
* Server event notifications
* Setup options for system specific configurations
* Leverage WP-CLI to manage WordPress Sites
* And some Drupal stuff
* Support MongoDB

