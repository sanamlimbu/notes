# Deployment process 

## Make server

- Make server
- Add user (adduser nii236)
- Add to sudoers (usermod -aG sudo nii236)
- Remove password requirement for sudoers (visudo)
- Add public key to created user (vim ~/.ssh/authorized_keys)
- Remove root ssh (vim /etc/ssh/sshd_config)
- Test SSH with user (ssh interns.theninja.life)
- Install postgres (sudo apt install postgresql)

## Frontend

- SCP binary (scp {source} host:{target})
- Rsync web to home folder (rsync -avz {source} host:{target})
- Install nginx (sudo apt install nginx)
- Add A record for domain (name.com)
- Add config for nginx to sites-available (vim /etc/nginx/sites-available/interns.theninja.life)
- Rsync app to system folder (sudo mkdir -p /var/www/interns.theninja.life/html && rsync -a ~/web/ /var/www/interns.theninja.life/html/)
- Add symlink for nginx sites-enabled (cd /etc/nginx/sites-enabled && ln -s /etc/nginx/sites-available/interns.theninja.life .)
- Test nginx (sudo nginx -t)
- Reload nginx (sudo systemctl reload nginx)
- Test the URL (curl interns.theninja.life)
- Install letsencrypt (sudo snap install certbot)
- Install certs (sudo cerbot)

## Useful commands

```
-systemctl
-journalctl
-ls
-cat
-grep
-find
-locate
-cp
-scp
-rsync
-vim
```
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
