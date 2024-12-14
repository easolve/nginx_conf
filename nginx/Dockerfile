FROM alpine:3.21

RUN apk update && \
    apk add --no-cache nginx && \
    mkdir -p /etc/nginx/ssl /var/www/nginx/.well-known

# Copy the configuration file
COPY conf/easerve.conf /etc/nginx/http.d/default.conf
COPY conf/n8n.conf /etc/nginx/http.d/n8n.conf
COPY ssl/origin.pem /etc/nginx/ssl/origin.pem
COPY ssl/origin.key /etc/nginx/ssl/origin.key

COPY assetlinks.json /var/www/nginx/.well-known/assetlinks.json

# Port to expose, Just documentation(Not necessary)
EXPOSE 443/tcp

CMD ["nginx", "-g", "daemon off;"]
