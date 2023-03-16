## Laravel Dockerfile and docker-compose

### What you need to modify before start your dev project

Modify \<hostPort> in docker-file with the port from your local machine you want to use for laravel

```
...
    ports:
        - 90:80
```

<b>Remember to create your <i>.env.dev</i> before the build!</b>

### How to create and start the container

```
docker-compose up -d
```

If you need to recreate the image, not using the Docker cache:

```
docker-compose build --no-cache && docker-compose up -d
```