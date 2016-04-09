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

Other than that... it doesn't work yet.
