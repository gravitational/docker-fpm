FROM centos:8

RUN set -x \
    && yum install -y ruby-devel rubygems gcc make rpmdevtools rpm-sign \
    && gem install fpm \
    && yum clean all \
    && mkdir /src

WORKDIR /src/

CMD /usr/local/bin/fpm
