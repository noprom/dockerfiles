FROM daocloud.io/centos:centos7.2.1511
MAINTAINER "noprom" <tyee.noprom@qq.com>
# Install Software
RUN rpm -iUvh http://dl.fedoraproject.org/pub/epel/7/x86_64/e/epel-release-7-8.noarch.rpm
RUN rpm -iUvh http://www6.atomicorp.com/channels/atomic/centos/7/x86_64/RPMS/atomic-release-1.0-21.el7.art.noarch.rpm
RUN yum -y install gcc gcc-c++ autoconf automake make zlib zlib-devel openssl openssl-devel pcre pcre-devel ack screen wget curl zip unzip ntpdate net-snmp net-snmp-devel net-snmp-utils vim git git-common nc htop iotop iftop telnet net-tools zsh python-pip python-devel sqlite-devel mysql-devel
RUN pip install --upgrade pip 
RUN pip install scrapy scrapy-redis pysqlite MySQL-python supervisor
WORKDIR /app
# For supervisor
RUN mkdir -p /etc/supervisor/conf.d && mkdir -p /var/log/supervisor
ADD supervisor.gp.conf /etc/supervisor/conf.d/
RUN echo_supervisord_conf > /etc/supervisord.conf && \
echo "files = /etc/supervisor/conf.d/*.conf" >> /etc/supervisord.conf
ADD entrypoint.sh /
CMD ["sh", "/entrypoint.sh"]
EXPOSE 3306
VOLUME ["/app"]