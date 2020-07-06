# ruby-first-app

## Installing Ruby on Rails

### Ruby
`sudo apt install ruby`


### SQLite
`sudo apt install sqlite3 libsqlite3-dev`


### Node.js
`sudo apt install nodejs`


### Yarn
`curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -`
`echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list`

`sudo apt remove cmdtest`

`sudo apt install yarn`


### Rails

Installing addintional packages for Rails
`sudo apt install gcc g++ make zlib1g-dev`

Installing Rails
`sudo gem install rails`


#### Bundler for Ruby
[Bundler](https://bundler.io/) provides a consistent environment for Ruby projects by tracking and installing the exact gems and versions that are needed. 
`sudo gem install bundler`

Installing gems
`sudo bundle install`


#### Webpacker
`sudo rails webpacker:install`


#### MySQL Adapter
`sudo apt install libmysqlclient-dev`

`sudo gem install mysql2`

After that need to add configuration data to `config/database.yml`
```
development:
  adapter: mysql2
  encoding: utf8
  database: [DB_NAME]
  username: root
  password: ''
  host: 127.0.0.1
  port: 3306
```

#### Postgresql Adapter
`sudo apt-get install libpq-dev`
`sudo gem install pg`

#### Starting webserver
`rails server`


## Installing MySQL
`sudo apt install mysql-server mysql-client`

### Root user reset password
```
sudo /etc/init.d/mysql stop # stop mysql service
sudo mysqld_safe --skip-grant-tables & # start mysql without password
# enter -> go
mysql -u root # connect to mysql
```

```
use mysql; # use mysql table
update user set authentication_string=PASSWORD("") where User='root'; # update password to nothing
update user set plugin="mysql_native_password" where User='root'; # set password resolving to default mechanism for root user

flush privileges;
quit;
```

```
sudo /etc/init.d/mysql stop 
sudo /etc/init.d/mysql start # reset mysql
# try login to database, just press enter at password prompt because your password is now blank
mysql -u root -p 
```

### Start MySQL

`sudo systemctl start mysqld.service` - start MySQL
`sudo systemctl enable mysqld.service` - enable autostart

## Dbeaver

[jre](https://www.java.com/ru/download/windows-64bit.jsp)
[dbeaver](https://dbeaver.io/)

## VSCode
Problem with remote-wsl permission denied
`sudo chown -R USER_NAME /path/to/project/`
