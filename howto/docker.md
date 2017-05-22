# Howto Docker

## Connect to a running container

Get the `container-id` using the following command:

```bash
docker ps # List all the container with their IDs.
```

Then, open a shell into the container using one of these commandes:

```bash
docker exec -it <container-id> bash # If the container does have bash installed
docker exec -it <container-id> sh # If the container doesn't have bash installed
```

## Docker-compose commands

```bash
docker-compose ps # List all running container managed by docker-compose
docker-compose up -d # Create and start in detached mode all the container defined inside the docker-compose.yml file.
docker-compose down # Stop and delete all the containers.
docker-compose rm <container-name> # Stop and delete a specific container.
docker-compose stop # Stop all containers.
docker-compose start # Start all containers.
```
