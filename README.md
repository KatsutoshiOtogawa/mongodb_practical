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
  },
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
  },
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
