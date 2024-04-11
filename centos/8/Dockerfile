FROM centos:8

RUN set -x \
    && sed -i \
        -e 's/^mirrorlist/#mirrorlist/g' \
        -e 's|#baseurl=http://mirror.centos.org|baseurl=http://vault.centos.org|g' \
        /etc/yum.repos.d/CentOS-* \
    && yum module -y enable ruby:3.0 \
    && yum install -y ruby rubygems gcc make rpmdevtools rpm-sign \
    && gem install fpm -v 1.15.1 \
    && yum clean all \
    && mkdir /src

WORKDIR /src/

CMD /usr/local/bin/fpm
