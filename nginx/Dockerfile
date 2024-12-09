# https://stackoverflow.com/questions/49118579/alpine-dockerfile-advantages-of-no-cache-vs-rm-var-cache-apk
# https://wiki.alpinelinux.org/wiki/Alpine_Package_Keeper#Local_Cache
FROM alpine:3.21

RUN apk update && \
    apk add --no-cache nginx && \
    mkdir -p /etc/nginx/ssl

# Copy the configuration file
COPY conf/default.conf /etc/nginx/http.d/default.conf
COPY /etc/ssl/cloudflare /etc/nginx/ssl 

# Port to expose, Just documentation(Not necessary)
EXPOSE 443/tcp

CMD ["nginx", "-g", "daemon off;"]
