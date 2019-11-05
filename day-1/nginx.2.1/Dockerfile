FROM centos 
LABEL maintainer="Alexey Silnikov"
RUN yum update -y && yum install nginx -y && yum clean all #&& echo "\ndaemon off;" >> /etc/nginx/nginx.conf
VOLUME /etc/nginx/sites-enabled
VOLUME /var/log/nginx
WORKDIR /etc/nginx
COPY default.conf /etc/nginx/conf.d/
#COPY nginx.conf /etc/nginx/ 
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
