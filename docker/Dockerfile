#################################################################
# Dockerfile to build Zimbra Collaboration 8.8.7 container images
# Based on Ubuntu 16.04
# Created by Jorge de la Cruz
#################################################################
FROM ubuntu:16.04
MAINTAINER Mateus Jesus <mateus.jesus@salvadorcard.com.br>

RUN echo "resolvconf resolvconf/linkify-resolvconf boolean false" | debconf-set-selections

RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get -y install \
  vim \
  tzdata \
  iputils-ping \
  libperl5.22 \
  sysstat \
  sqlite3 \
  pax \
  libhttp-date-perl \
  libgetopt-mixed-perl \
  libgmp10 \
  libmime-explode-perl \
  file \
  lvm2 \
  libaio1 \
  wget \
  dialog \
  openssh-client \
  software-properties-common \
  dnsmasq \
  dnsutils \
  net-tools \
  sudo \
  rsyslog \
  unzip
  
RUN echo "America/Bahia" > /etc/timezone && rm /etc/localtime && dpkg-reconfigure -f noninteractive tzdata

VOLUME ["/opt/zimbra"]

EXPOSE 22 25 465 587 110 143 993 995 80 443 8080 8443 7071

COPY opt /opt/

COPY etc /etc/

CMD ["/bin/bash"]
