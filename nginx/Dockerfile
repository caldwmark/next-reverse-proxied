FROM nginx:stable-alpine

COPY ./conf/nginx.conf /etc/nginx/nginx.conf
COPY ./conf/bearcountry.conf /etc/nginx/conf.d/
RUN mkdir -p /data/nginx/cache

EXPOSE 8088

