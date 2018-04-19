# BitBake for Yocto builds, based on Debian

FROM    debian
LABEL \
 Description="BitBake for Yocto builds. Image based on Debian." \
 MAINTAINER="Thomas Thorne <TafThorne@GoogleMail.com>"
RUN apt-get update && apt-get -y install \
 build-essential \
 chrpath \
 cpio \
 debianutils \
 diffstat \
 gawk \
 gcc-multilib \
 git-core \
 iputils-ping \
 locales \
 python \
 python3 \
 python3-pip \
 python3-pexpect \
 socat \
 texinfo \
 unzip \
 wget \
 xz-utils
RUN sed -i -e 's/# en_US.UTF-8 UTF-8/en_US.UTF-8 UTF-8/' /etc/locale.gen \
 && echo 'LANG="en_US.UTF-8"'>/etc/default/locale \
 && dpkg-reconfigure --frontend=noninteractive locales \
 && update-locale LANG=en_US.UTF-8

ENV LANG en_US.UTF-8
ENV LANGUAGE en_US.UTF-8
ENV LC_ALL en_US.UTF-8

RUN adduser builder

USER builder
WORKDIR /home/builder

