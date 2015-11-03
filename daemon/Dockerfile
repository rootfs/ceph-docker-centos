FROM cephdaemon/base
MAINTAINER Huamin Chen <hchen@redhat.com>

# Add bootstrap script
ADD config.*.sh /

# Add volumes for Ceph config and data
VOLUME ["/etc/ceph","/var/lib/ceph"]

ADD entrypoint.sh /entrypoint.sh
# Execute the entrypoint
WORKDIR /
ENTRYPOINT ["/entrypoint.sh"]