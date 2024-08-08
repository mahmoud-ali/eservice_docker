# Commands for management

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
cd {hr_folder}
```
```
sudo tar czf /home/mahmoud/hr_backup_`date -I`.tar.gz data/ upload/
```
## Encrypt and zip data
```
cd {hr_folder}
```
```
sudo tar cf - data/ upload/|gpg -c > hr_backup_`date -I`.tar.gpg
```
