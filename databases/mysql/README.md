## MySQL dev container

### What you need to modify from docker-compose before run

You will find the following lines in your docker-compose file:

```
...
 environment:
      - MYSQL_DATABASE=<databaseName>
      - MYSQL_ROOT_PASSWORD_FILE=/run/secrets/db-password
...
    secrets:
      - db-password
...
secrets:
  db-password:
    file: db/password.txt
...

    networks:
      - <backend>-mariadb
...
networks:
  <backend>-mariadb: {}
...
```

What is needed here:
- You need to replace \<databaseName> with the name of your own database
- You need to create a db-password.txt file in a (root project folder)/db folder, to share the database password with the container
- Replace \<backend> with the name of the backend you are using. You may add the backend to this docker-compose and use the same network. Comment these lines if no needed to use them.

### How to create and start the container

```
docker-compose up -d
```

If you need to recreate the image, not using the Docker cache:

```
docker-compose build --no-cache && docker-compose up -d