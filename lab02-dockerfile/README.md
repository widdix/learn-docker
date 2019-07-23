# Lab 02: Dockerfile

## Goal

Build a custom Docker image that serves a static website using nginx.

## Instructions

Make sure you are starting from the Lab 02 directory `lab02-dockerfile`.

```
cp lab02-dockerfile/starting-point/Dockerfile Dockerfile
```

Extend the Dockerfile with the following instructions.

### Add default.conf

Copy the `default.conf` file into nginx's configuration directory that is included when nginx starts (`/etc/nginx/conf.d/`).

### Add static files

Copy the content of the `website` folder to `/var/www/html`.

### Change ownership of copied files

All files where copied by root so far. Nginx runs as user and group `nginx`. Change the owner of the files in `/var/www/html` to `nginx`.

### Build the image

Now it's time to build the image.

```
docker build -t workshop:latest .
```

### Test the image

Let's see if it works. Start a container based on your new image.

```
docker run -d --rm -p 8080:80 workshop:latest
```

And visit `http://localhost:8080` on your machine.

# Help

* Dockerfile instruction [COPY](https://docs.docker.com/engine/reference/builder/#copy)
* Dockerfile instruction [RUN](https://docs.docker.com/engine/reference/builder/#run)
* Docker CLI [build](https://docs.docker.com/engine/reference/commandline/build/)
* Docker CLI [run](https://docs.docker.com/engine/reference/commandline/run/)
