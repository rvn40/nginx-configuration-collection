FROM nginx:stable-alpine3.17

# twb-admin-01:BUqi4jOgxTmP1npL
RUN apk --no-cache --update add apache2-utils vim curl && \
	cp /usr/share/zoneinfo/UTC /etc/localtime && \
	echo "UTC+7" > /etc/timezone && \
	apk del tzdata

COPY basic-auth-proxy/html/index.html /usr/share/nginx/html/index.html
COPY basic-auth-proxy/html/fail.html /usr/share/nginx/html/fail.html
COPY basic-auth-proxy/nginx.conf /etc/nginx/conf.d/default.conf
COPY basic-auth-proxy/htpasswd /etc/nginx/.htpasswd
