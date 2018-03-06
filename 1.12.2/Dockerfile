FROM nginx:1.12.2-alpine
MAINTAINER WPLib Team <team@wplib.org>

# Change user from "nginx" to "vagrant"
# This isn't really required, but good for cases where nginx is used standalone.
RUN apk update && \
	apk add --no-cache less bash shadow && \
	groupadd -g 1000 vagrant && \
	mkdir /var/mail && \
	useradd -d /var/cache/nginx -c "WPLib vagrant user" -u 1000 -g 1000 -N -s /bin/bash vagrant && \
	chown -fhR vagrant:vagrant /var/cache/nginx /var/log/nginx /etc/nginx /usr/lib/nginx /usr/sbin/nginx /usr/share/nginx

COPY files /

EXPOSE 80 443
