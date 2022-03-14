# Wordpress setup docker compose

## Dependancy

docker, docker-compose

## Setup

### Install docker and docker compose

```bash
bash setup.sh
#Verify that docker and docker-compose work correctly
docker run hello-world
docker-compose --version
```

### Start

```bash
docker-compose up --remove-orphans -d #remove -d flag to show logs on terminal
```

### Stop

```bash
docker-compose down --remove-orphans
```

### Stop and remove persistence data. WARNING!!! THIS COMMAND WILL DELETE YOUR WORDPRESS DATA

```bash
#WARNING!!! THIS COMMAND WILL DELETE YOUR WORDPRESS DATA
docker-compose down --remove-orphans -v
```

### Backup and restore data

```bash
#backup
sudo tar -czf backup.tar.gz /var/lib/docker/volumes/wp_db_data /var/lib/docker/volumes/wp_wordpress_data
#restore
sudo tar -xzf backup.tar.gz -C /
```
