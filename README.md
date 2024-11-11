# Commands for management
change directory to a directory with `compose.yaml` file (ex: `cd hr`). 

## Stop running containers
```
docker compose stop
```
## Start with build
```
docker compose up --build -d
```
## Backup hr data
```
cd /home/mahmoud/hr_compose

rm /tmp/db.sql
docker compose exec db pg_dump my_db -h localhost -U my_user > /tmp/db.sql
/usr/bin/tar czf /home/mahmoud/sharefolder/backup_`date -I`.tar.gz /tmp/db.sql /home/mahmoud/hr_compose/upload/
```
## Encrypt and zip data
```
sudo tar cf - data/ upload/|gpg -c > hr_backup_`date -I`.tar.gpg
```
