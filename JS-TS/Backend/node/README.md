## Node.js dev container

### What you need to modify from docker-compose before go

```
ports:
      - <portHost>:<portContainer>
    container_name: node
    command: bash -c 'npm i && npm run <scriptName>'
```

Replace ``` \<portHost>:<portContainer> ``` with the ports from your machine : from the container you want to use
Replace ``` \<scriptName> ``` with the name of your start dev script

### How to create and start the container

```
docker-compose up -d
```

If you need to recreate the image, not using the Docker cache:

```
docker-compose build --no-cache && docker-compose up -d