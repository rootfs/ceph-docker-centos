FROM centos:7

MAINTAINER Huamin Chen <hchen@redhat.com>

RUN yum --setopt=tsflags=nodocs -y update && yum --setopt=tsflags=nodocs -y install wget openssh openssh-server openssh-clients hostname epel-release
RUN yum clean all


RUN rpm -Uvh http://download.ceph.com/rpm/rhel7/noarch/ceph-release-1-1.el7.noarch.rpm
RUN yum install --setopt=tsflags=nodocs -y install ceph
RUN yum clean all

RUN echo 'root:password' | chpasswd

ENTRYPOINT /usr/bin/sleep infinity