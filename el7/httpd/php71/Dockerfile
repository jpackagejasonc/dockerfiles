FROM centos:7
MAINTAINER The CentOS Project <cloud-ops@centos.org>
LABEL Vendor="CentOS" \
      License=GPLv2 \
      Version=2.4.6-40


RUN yum clean all
RUN yum -y --setopt=tsflags=nodocs update
RUN yum -y --setopt=tsflags=nodocs install \
    https://centos7.iuscommunity.org/ius-release.rpm
RUN yum -y --setopt=tsflags=nodocs install \
    httpd \
    mod_php71u \
    pear1u \
    php71u-bcmath \
    php71u-cli \
    php71u-common \
    php71u-gd \
    php71u-imap \
    php71u-ldap \
    php71u-mbstring \
    php71u-mcrypt \
    php71u-mysqlnd \
    php71u-opcache \
    php71u-pdo \
    php71u-pecl-igbinary \
    php71u-pecl-memcached \
    php71u-process \
    php71u-soap php71u-xml

EXPOSE 80

# Simple startup script to avoid some issues observed with container restart
ADD run-httpd.sh /run-httpd.sh
ADD index.php /var/www/html/index.php
RUN chmod -v +x /run-httpd.sh

CMD ["/run-httpd.sh"]
