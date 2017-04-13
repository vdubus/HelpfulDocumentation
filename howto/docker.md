# Howto Docker

## Connect to a running container

Get the `container-id` using the following command:

```bash
docker ps
```

Then, open a shell into the container using one of these commandes:

```bash
docker exec -it <container-id> bash # If the container does have bash installed
docker exec -it <container-id> sh # If the container doesn't have bash installed
```
