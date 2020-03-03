
#How to get started with MySQL on Debian 10
The configuration of MySQL is straightforward, but the 
latest versions are not available on the stardard pre-configured repo 
of Debian 10.
On 2020/03/03 the latest is MySQL v8.0.19.

## Install
First thing to do is add the repos through deb packages.

> wget,sudo are needed here

It's not really mandatory to get the latest debs because a combo
```bash
$ sudo apt update
$ sudo apt upgrade
```
will set them to the latest after installing the repos.
The update will also provide a list of the new versions to be installed at
```bash
$ apt list --upgradable
```
We just go get a deb and we install it
```bash
$ FILEPATH=https://repo.mysql.com/mysql-apt-config_0.8.13-1_all.deb
$ wget FILEPATH 
$ IFS='/'
$ read -ra PARTS <<< "$FILEPATH"
$ len=${#PARTS[@]}
$ FILENAME=${PARTS[${len}-1]}
$ sudo dpkg -i $FILENAME
```
beside this is formative and awfully complicated. We could rather do a simple
```bash
$ wget path/file
$ sudo dpkg -i file
```
Anyway on launch we get to configure a bunch of things that are fine as they are 
as per default. It is recommendable to leave the password field blank for **root**.
The invocation of `mysql -u root` can be done only as sudoer.
The installation then requires 
```bash
$ sudo apt update
$ sudo apt [-y] install mysql-server
```
and that's pretty much it. 
## First use
You might wanna get a daily user which is given by logging as root on mysql and 
```mysql
mysql> CREATE USER 'newuser'@'localhost' IDENTIFIED BY 'user_password';
```
in case of privilege granting we might add
```mysql 
mysql> GRANT ALL PRIVILEGES ON database_name.* TO 'database_user'@'localhost';
```

