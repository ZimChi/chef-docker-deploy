#modified from https://github.com/dockerfile/nginx

FROM ubuntu:16.04

RUN apt-get update && apt-get install -y --no-install-recommends software-properties-common

RUN \
add-apt-repository -y ppa:nginx/stable && \
apt-get update && \
apt-get install -y nginx && \
rm -rf /var/lib/apt/lists/* && \
echo "\ndaemon off;" >> /etc/nginx/nginx.conf && \
chown -R www-data:www-data /var/lib/nginx

VOLUME ["/etc/nginx/sites-enabled", "/etc/nginx/certs", "/etc/nginx/conf.d", "/var/log/nginx", "/var/www/html"]

ADD test-app.txt /var/www/html/test-app.txt

WORKDIR /etc/nginx

CMD ["nginx"]

EXPOSE 80
EXPOSE 443
