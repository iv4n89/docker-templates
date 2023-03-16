## Spring boot container

This container runs Spring boot production build!

### What you need to modify from Dockerfile before running container

You will find this line at the end of the Dockerfile:

```
ENTRYPOINT ["java","-cp","app:app/lib/*","com.<company>.<project>.<Application>"]
```

You need to replace the \<something> parts with your own class (main class name from your project)

Example:

```
ENTRYPOINT ["java","-cp","app:app/lib/*","com.myCompany.myProject.Application"]
```

### How to create and start the container

```
docker-compose up -d
```

If you need to recreate the image, not using the Docker cache:

```
docker-compose build --no-cache && docker-compose up -d