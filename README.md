# Simple Nginx website

A responsive HTML and CSS page packaged in an Nginx Docker image.

## Build and run

With Docker running, execute these commands from this directory:

```sh
docker build -t simple-nginx-page .
docker run --detach --name simple-nginx-page -p 8080:80 simple-nginx-page
```

Open http://localhost:8080 in your browser.

## Customize

Edit `dist/index.html`, then rebuild the image and recreate the container:

```sh
docker rm -f simple-nginx-page
docker build -t simple-nginx-page .
docker run --detach --name simple-nginx-page -p 8080:80 simple-nginx-page
```

## Stop and remove the container

```sh
docker stop simple-nginx-page
docker rm simple-nginx-page
```

The image uses the official `nginx:stable-alpine` base image and serves the page on container port 80.
