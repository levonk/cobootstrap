FROM debian:jessie
MAINTAINER Levon Karayan

RUN apt-get update && apt-get install -y nginx && rm -rf /var/lib/apt/lists/*

COPY conf/jenkins.conf /etc/nginx/conf.d/jenkins.conf
COPY conf/nginx.conf /etc/nginx/nginx.conf

EXPOSE 80 443

CMD ["nginx"]

