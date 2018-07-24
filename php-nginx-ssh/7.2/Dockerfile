FROM webdevops/php-nginx:7.2
MAINTAINER Pranjal Jain <pranjal.jain@tothenew.com>


ENV LOG_STDOUT=/var/log/nginx/access.log
ENV LOG_STDERR=/var/log/nginx/error.log
ENV WEB_DOCUMENT_ROOT=/var/www/html/

RUN apt-get update && apt-get install -y openssh-server
RUN mkdir -p /var/run/sshd
RUN echo 'root:admin@123' | chpasswd

RUN sed -i 's/#PermitRootLogin prohibit-password/PermitRootLogin yes/' /etc/ssh/sshd_config 

ADD ssh.conf /opt/docker/etc/supervisor.d/
ADD index.php /var/www/html/

EXPOSE 22 




