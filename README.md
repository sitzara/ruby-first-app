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

`sudo apt install gcc g++ make zlib1g-dev`

And finaly

`sudo gem install rails`

#### Bundler for Ruby
[Bundler](https://bundler.io/) provides a consistent environment for Ruby projects by tracking and installing the exact gems and versions that are needed. 

`sudo gem install bundler`

`sudo bundle install` - installing gems

#### Webpacker
`sudo rails webpacker:install`

#### MySQL Adapter
`sudo apt install libmysqlclient-dev`
`sudo gem install mysql2`

#### Starting webserver
`rails server`


## Installing MySQL
`sudo apt install mysql-server`

`sudo apt install mysql-client`

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

## Dbeaver

[jre](https://www.java.com/ru/download/windows-64bit.jsp)
[dbeaver](https://dbeaver.io/)
