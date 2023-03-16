## MongoDB dev container

### What you need to modify from docker-compose before you go

```
...
# networks:
#   - <backend>-mongo
...
# networks:
#   <backend>-mongo: {}
...
```

Uncomment the above lines if you need them.
Replace \<backend> from the network name with the framework name you have in use, and add the backend service to this docker-compose file.
Add the same network to the backend service.

### How to create and start the container

```
docker-compose up -d
```

If you need to recreate the image, not using the Docker cache:

```
docker-compose build --no-cache && docker-compose up -d