#
# MAINTAINER          Max
# DOCKER-VERSION      1.10
# CENTOS-VERSION      6.7
# Dockerfile-VERSION  1.0
# DATE                02/25/2016
# SHOPEX LAMP
# Apache Verison      2.22
# PHP verison         5.6
# Mysql Version       5.1

FROM centos:6.7
MAINTAINER Max

ENV TZ "Asia/Shanghai"
ENV TERM xterm

ADD shopex-lnmp.repo /etc/yum.repos.d/shopex-lnmp.repo
ADD aliyun-epel.repo /etc/yum.repos.d/epel.repo
ADD shopex-php56.repo /etc/yum.repos.d/shopex-php56.repo

RUN yum -y update

RUN yum -y install openssh-server htop nano screen httpd mysql php php-pdo php-xml php-soap php-fpm php-bcmath php-common php-mysql php-mcrypt php-mbstring php-gd php-cli php-xmlrpc php-pecl-igbinary php-pecl-redis php-pecl-mongo php-pecl-memcache php-pecl-memcached php-ZendGuardLoader memcached redis && \
    ssh-keygen -q -N "" -t rsa -f /etc/ssh/ssh_host_rsa_key && \
    ssh-keygen -q -N "" -t rsa -f /etc/ssh/ssh_host_dsa_key && \
    sed -i "s/#UsePrivilegeSeparation.*/UsePrivilegeSeparation no/g" /etc/ssh/sshd_config && \
    sed -i "s/UsePAM.*/UsePAM yes/g" /etc/ssh/sshd_config

RUN ls /etc/php.d/60-zend.ini

ADD my.cnf /usr/local/mysql51/my.cnf

ADD set_root_pw.sh /set_root_pw.sh
ADD run.sh /run.sh
RUN chmod +x /*.sh

ENV AUTHORIZED_KEYS **None**
ENV ROOT_PASS LNMP123

VOLUME ["/home"]

EXPOSE 80 21 22 3306 6379 11211

CMD ["/run.sh"]
