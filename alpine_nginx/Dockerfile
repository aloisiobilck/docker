FROM alpine:latest
MAINTAINER Aloisio Bilck <aloisio.bilck@bry.com.br>


# Install Nginx and rsyslog
RUN apk add --update nginx && apk add --update rsyslog  && rm -rf /var/cache/apk/* 
RUN mkdir -p /tmp/nginx/client-body && mkdir -p /service/rsyslog

COPY nginx/nginx.conf /etc/nginx/nginx.conf
COPY nginx/default.conf /etc/nginx/conf.d/default.conf
COPY website /usr/share/nginx/html

COPY rsyslog.conf /etc/rsyslog.conf
COPY run.sh /service/rsyslog/run

EXPOSE 514/tcp

CMD ["nginx", "-g", "daemon off;"]
