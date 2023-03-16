## NestJS dev container

### How to change from `dev` to `production` in docker-file

Replace ``` target: development ``` with ``` target: production ```
Replace ``` command: npm run start:dev ``` with ``` npm run start ```

### How to create and start the container

```
docker-compose up -d
```

If you need to recreate the image, not using the Docker cache:

```
docker-compose build --no-cache && docker-compose up -d