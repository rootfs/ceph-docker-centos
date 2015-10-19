FROM centos:7

MAINTAINER Huamin Chen <hchen@redhat.com>

RUN yum --setopt=tsflags=nodocs -y update && yum --setopt=tsflags=nodocs -y install wget openssh openssh-server openssh-clients hostname epel-release
RUN yum clean all


RUN rpm -Uvh http://download.ceph.com/rpm/rhel7/noarch/ceph-release-1-1.el7.noarch.rpm
RUN yum install --setopt=tsflags=nodocs -y install ceph

# see http://developerblog.redhat.com/2014/05/05/running-systemd-within-docker-container/
RUN yum -y swap -- remove systemd-container systemd-container-libs  -- install systemd systemd-libs
RUN yum -y update; yum clean all; \
(cd /lib/systemd/system/sysinit.target.wants/; for i in *; do [ $i == systemd-tmpfiles-setup.service ] || rm -f $i; done); \
rm -f /lib/systemd/system/multi-user.target.wants/*;\
rm -f /etc/systemd/system/*.wants/*;\
rm -f /lib/systemd/system/local-fs.target.wants/*; \
rm -f /lib/systemd/system/sockets.target.wants/*udev*; \
rm -f /lib/systemd/system/sockets.target.wants/*initctl*; \
rm -f /lib/systemd/system/basic.target.wants/*;\
rm -f /lib/systemd/system/anaconda.target.wants/*;


ENTRYPOINT /usr/bin/sleep infinity