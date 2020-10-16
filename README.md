# create-react-app

![Node.js CI](https://github.com/scorpion/create-react-app/workflows/Node.js%20CI/badge.svg)

Template - https://create-react-app.dev

## Local Development

You can perform local development with live reloading.

`yarn start`

Go to <http://localhost:3000>

## Docker

```dockerfile
docker-compose up -d --build
```

### Command Breakdown

|                  |                                                                                                                            |
| ---------------- | -------------------------------------------------------------------------------------------------------------------------- |
| `docker-compose` | [Docker Compose](https://docs.docker.com/compose/) is a tool for defining and running multi-container Docker applications. |
| `up`             | The [up](https://docs.docker.com/compose/reference/up/) command aggregates the output of each container.                   |
| `-d`             | Detached mode: Run containers in the background, print new container names.                                                |
| `--build`        | Build images before starting containers.                                                                                   |

Builds, (re)creates, starts, and attaches to containers for a service.

Unless they are already running, this command also starts any linked services.

The `docker-compose up` command aggregates the output of each container (essentially running `docker-compose logs -f`). When
the command exits, all containers are stopped. Running `docker-compose up -d`
starts the containers in the background and leaves them running.

If there are existing containers for a service, and the service's configuration
or image was changed after the container's creation, `docker-compose up` picks
up the changes by stopping and recreating the containers (preserving mounted
volumes). To prevent Compose from picking up changes, use the `--no-recreate`
flag.

If you want to force Compose to stop and recreate all containers, use the
`--force-recreate` flag.

If the process encounters an error, the exit code for this command is `1`.  
If the process is interrupted using `SIGINT` (`ctrl` + `C`) or `SIGTERM`, the containers are stopped, and the exit code is `0`.  
If `SIGINT` or `SIGTERM` is sent again during this shutdown phase, the running containers are killed, and the exit code is `2`.
