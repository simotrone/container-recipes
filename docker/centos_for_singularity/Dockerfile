FROM centos:7.3.1611

LABEL maintainer="simotrone"
LABEL version="2.4"

# fix man + generic distro packages
# need localedef only for centos 7.3.1611
RUN useradd sim \
 && sed -e '/tsflags/ s/^#*/# /' -i /etc/yum.conf \
 && yum -y install deltarpm \
 && yum -y update \
 && localedef -i en_US -f UTF-8 en_US.UTF-8 \
 && yum -y install \
      man man-pages \
      curl \
      git \
      less \
      lsof \
      lynx \
      nmap-ncat \
      perl-CPAN \
			strace \
      tree \
      vim \
      wget \
      yum-utils

EXPOSE 3306 8080

WORKDIR /root

# singularity
RUN yum -y groupinstall 'Development Tools' --setopt=group_package_types=mandatory,default,optional \
 && yum -y install libarchive-devel squashfs-tools

# singularity as root
RUN git clone https://github.com/sylabs/singularity.git \
 && cd singularity \
 && git fetch --all \
 && git checkout 2.6.0 \
 && ./autogen.sh \
 && ./configure --prefix=/usr/local \
 && make install

