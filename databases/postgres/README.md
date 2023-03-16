## PostgreSQL dev container

### What you need to modify from docker-compose file before go

```
...
    environment:
      - POSTGRES_PASSWORD=<password>
      - POSTGRES_DB=<database>
      - POSTGRES_USER=<user>
...
```

Replace the \<something> with the data from your database

### How to create and start the container

```
docker-compose up -d
```

If you need to recreate the image, not using the Docker cache:

```
docker-compose build --no-cache && docker-compose up -d