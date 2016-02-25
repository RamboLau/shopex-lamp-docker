#
# MAINTAINER          Max
# DOCKER-VERSION      1.10
# CENTOS-VERSION      6.7
# Dockerfile-VERSION  1.0
# DATE                02/24/2016
# SHOPEX LAMP
# Apache Verison      2.22
# PHP verison         5.3.29
# Mysql Version       5.1

FROM centos:6.7
MAINTAINER Max

ENV TZ "Asia/Shanghai"
ENV TERM xterm

ADD shopex-lnmp.repo /etc/yum.repos.d/shopex-lnmp.repo
ADD aliyun-epel.repo /etc/yum.repos.d/epel.repo

RUN yum -y update

RUN yum -y install openssh-server htop nano screen httpd php-pdo php-xml php-pecl-imagick php-soap php php-fpm php-bcmath php-pecl-memcached php-pecl-igbinary php-common php-mysql php-mcrypt php-mbstring php-pecl-memcache php-pecl-redis php-gd php-cli php-xmlrpc php-pecl-mongo php-ZendGuardLoader mysql51 redis memcached php-pthreads && \
    ssh-keygen -q -N "" -t rsa -f /etc/ssh/ssh_host_rsa_key && \
    ssh-keygen -q -N "" -t rsa -f /etc/ssh/ssh_host_dsa_key && \
    sed -i "s/#UsePrivilegeSeparation.*/UsePrivilegeSeparation no/g" /etc/ssh/sshd_config && \
    sed -i "s/UsePAM.*/UsePAM yes/g" /etc/ssh/sshd_config

ADD my.cnf /usr/local/mysql51/my.cnf

ADD set_root_pw.sh /set_root_pw.sh
ADD run.sh /run.sh
RUN chmod +x /*.sh

ENV AUTHORIZED_KEYS **None**
ENV ROOT_PASS LNMP123

VOLUME ["/home"]

EXPOSE 80 21 22 3306 6379 11211

CMD ["/run.sh"]
