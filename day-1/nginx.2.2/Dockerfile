FROM ubuntu
MAINTAINER "Alexey Silnikov"
RUN apt-get update -y && apt-get install -y software-properties-common && add-apt-repository -y ppa:nginx/stable && apt-get update -y && apt-get install -y nginx  && apt clean all
RUN ln -s /dev/stdout /var/log/nginx/access_log && \
    ln -s /dev/stderr /var/log/nginx/error_log
VOLUME /etc/nginx/sites-enabled
VOLUME /var/log/nginx
WORKDIR /etc/nginx
COPY default.conf /etc/nginx/conf.d/default.conf
COPY nginx.conf /etc/nginx/nginx.conf
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
