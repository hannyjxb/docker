# Simple web app for Pluralsight courses and Docker Deep Dive book
This is a quick and dirty node.js app cobbled together for the purposes of demonstrating how to Dockerize/containerize a simple app.

**This app is not maintained and WILL be full of vulnerbilities. Use at own risk**

Exposes web server on port 8080 as per ./app.js

See **Dockerfile** for more details

Build the image with command `docker image built -t test:latest .`

Start the container with the image `docker container run -d --name web1 --publish 8080:8080 test:latest`

Open your browser and visit the application via localhost:8080
