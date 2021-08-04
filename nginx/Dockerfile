FROM centos:8

RUN yum update -y && yum install nginx -y && yum clean all && mkdir -p /var/www/html

COPY nginx.conf /etc/nginx/nginx.conf
COPY default.conf /etc/nginx/conf.d/default.conf

EXPOSE 8081

CMD ["nginx", "-g", "daemon off;"]

