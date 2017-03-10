FROM centos:7
MAINTAINER The CentOS Project <cloud-ops@centos.org>
LABEL Vendor="CentOS" \
      License=GPLv2 \
      Version=2.4.6-40


RUN yum clean all
RUN yum -y --setopt=tsflags=nodocs update
RUN yum -y --setopt=tsflags=nodocs install epel-release
RUN yum -y --setopt=tsflags=nodocs install nginx
RUN echo "daemon off;" >> /etc/nginx/nginx.conf
RUN echo "nginx on CentOS 7 inside Docker" > /usr/share/nginx/html/index.html

EXPOSE 80

CMD ["/usr/sbin/nginx"]
