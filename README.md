
# Drone-server
This section provides basic instructions for installing Drone using docker-compose. The below configuration can be used to start the Drone server with multi-agent.

### Dependencies
- [x] [Drne CI](https://github.com/drone/drone)
- [x] [Docker](https://www.docker.com/)
- [x] [Docker Compose](https://docs.docker.com/compose/)

# Environment Variables Setting
* `copy .env.example .env `

 Modify .env conform your database setting

# Database Setting
- Sqlite
    - Delete `DRONE_DATABASE_DRIVER` and `DRONE_DATABASE_DATASOURCE` at docker-compose.yaml
- MariaDB
    - Set `DB_DRIVER=mysql`
    - Set `DB_HOST=mariadb`
    - Set `DB_DATABASE,DB_USERNAME,DB_PASSWORD,DB_ROOT_PASSWORD`
    - Copy MariaDB Connection command(at .env file) insert docker-compose.yaml `DRONE_DATABASE_DATASOURCE` field
- PostgreSQL
    - Set `DB_DRIVER=postgres`
    - Set `DB_HOST=postgres`
    - Set `DB_DATABASE,DB_USERNAME,DB_PASSWORD`
    - Copy PostgreSQL Connection command(at .env file) insert docker-compose.yaml `DRONE_DATABASE_DATASOURCE` field

# Start containers 
Start the containers in the background and leaves them running.
* `docker-compose up -d`

## Stops containers
Stops running containers without removing them
* `docker-compose stop `

## Stop and remove containers
Stops containers and removes containers, networks, volumes, and images created by up
* `docker-compose down `

## Log watching containers
Displays log output from services.
* `docker-compose logs -f`

## Local use drone cli

First [Install cli tool](http://docs.drone.io/cli-installation/)

```
$ export DRONE_SERVER=http://localhost/
$ export DRONE_TOKEN={YOUR_TOKEN}
$ drone info
User: cutedogspark
Email: cutedogspark@gmail.com
```

## Contributing

Contributions are most welcome! 
