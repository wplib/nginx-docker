FROM nginx:1.13.8-alpine
MAINTAINER WPLib Team <team@wplib.org>

RUN apk update && apk add less bash shadow

COPY files /

# Change user from "nginx" to "vagrant"
# This isn't really required, but good for cases where nginx is used standalone.
RUN groupadd -g 1000 vagrant && \
	useradd -d /var/cache/nginx -c "WPLib vagrant user" -u 1000 -g 1000 -N -s /bin/bash vagrant && \
	chown -fhR vagrant:vagrant /var/cache/nginx /var/log/nginx /etc/nginx /usr/lib/nginx /usr/sbin/nginx /usr/share/nginx

EXPOSE 80 443
