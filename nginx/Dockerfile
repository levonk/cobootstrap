FROM debian:jessie
MAINTAINER Levon Karayan

ARG user=nginx
ARG group=nginx
ARG uid=1000
ARG gid=1000

ENV NGINX_HOME /home/nginx

RUN apt-get update && apt-get install -y nginx && rm -rf /var/lib/apt/lists/*

COPY conf/jenkins.conf /etc/nginx/conf.d/jenkins.conf
COPY conf/nginx.conf /etc/nginx/nginx.conf

EXPOSE 80 443

USER root
RUN groupadd -g ${gid} ${group} \
		&& useradd -d "${NGINX_HOME}" -u ${uid} -g ${gid} -m -s /bin/bash ${user}
RUN mkdir -p /var/log/nginx; \
		chown -R ${user}:${group} /var/log/nginx

CMD ["nginx"]

