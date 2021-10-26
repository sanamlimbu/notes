# Deployment process 

## Frontend


## Backend

- Create database
```
CREATE DATABASE "boilerplate";
```
- Create db user with password 
```
CREATE USER "boilerplate" WITH PASSWORD 'draconian-notable-americangoldfinch';
```
- Assign DB to user
```
ALTER DATABASE boilerplate OWNER TO boilerplate;
```
- Configure database for external TCP connections (if required)
```
$ sudo vim /etc/postgresql/10/main/pg_hba.conf
```
- Initialise db extensions
- Migrate db

- Create service
- Move binary, migration, migrate tool files to /usr/share/{app_name}
- Run migrations
- Run server in foreground
- Test /api/check
- Stop server
- Enable service
- Start service
- Test /api/check
- Seed database
