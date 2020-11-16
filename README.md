# mongodb_practical
mongodb lesson

```
// Create Each database user, and database.
db.createUser(
  {
    user: "APP_TEST",
    pwd: "password",
    roles:
    [
      {
        role: "userAdmin",
        db: "APP_TEST"
      }
    ]
  }
)

db.createUser(
  {
    user: "APP_DEVELOPMENT",
    pwd: "password",
    roles:
    [
      {
        role: "userAdmin",
        db: "APP_DEVELOPMENT"
      }
    ]
  }
)

db.createUser(
  {
    user: "APP_PRODUCTION",
    pwd: "password",
    roles:
    [
      {
        role: "userAdmin",
        db: "APP_PRODUCTION"
      }
    ]
  }
)

// create database adminer.
db.createUser(
  {
    user: "db_admin",
    pwd: "password",
    roles:
    [
      {
        role: "userAdmin",
        db: "APP_TEST"
      },
      {
        role: "userAdmin",
        db: "APP_DEVELOPMENT"
      },
      {
        role: "userAdmin",
        db: "APP_PRODUCTION"
      }
    ]
  }
)

```

## 

if you want to login from external network.
if you use cloud,you set Security group and NetworkACL.
if you use host, you set selinux or apparmor and ufw or firewalld.
- modify /etc/mongo.conf file.
```
# bind_ip = 127.0.0.1
bind_ip = 0.0.0.0
```
- use gsed, 
```
sudo sed -i.org 's/^bind_ip = .*$/bind_ip = 0\.0\.0\.0/' /etc/mongodb.conf
```

## login mongodb
```
$ mongo [hostname]/[dbname] -u [username] -p [password]
```
