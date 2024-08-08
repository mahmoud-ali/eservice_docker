# Commands for management
change directory to a directory with `compose.yaml` folder (ex: `cd hr`). 

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
sudo tar czf /home/mahmoud/hr_backup_`date -I`.tar.gz data/ upload/
```
## Encrypt and zip data
```
sudo tar cf - data/ upload/|gpg -c > hr_backup_`date -I`.tar.gpg
```
