# Simple nginx image
FROM ubuntu:bionic

ENV NGINX_VERSION 1.14.0-0ubuntu1.6

RUN apt-get update && apt-get install -y curl
RUN apt-get update && apt-get install -y nginx=$NGINX_VERSION

#Adding index.html to the container
WORKDIR /var/www/html/
ADD index.html ./

EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]

#Stopsignal to terminate the process
STOPSIGNAL SIGTERM
HEALTHCHECK CMD curl localhost:80
