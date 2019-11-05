FROM alpine
LABEL maintainer="Alexey Silnikov"
RUN apk add --update nginx && rm -rf /var/cache/apk/* && mkdir -pv /run/nginx
VOLUME /etc/nginx/sites-enabled
VOLUME /var/log/nginx
WORKDIR /etc/nginx
COPY default.conf /etc/nginx/conf.d/
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]


