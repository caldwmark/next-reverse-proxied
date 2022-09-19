FROM alpine

WORKDIR /usr/bin

COPY ./ssl-proxy .

EXPOSE 80 443

CMD ["ssl-proxy", "-from", "0.0.0.0:443", "-to", "nginx:8088", "-domain=docker.bearcountrypublishing.com", "-redirectHTTP"]