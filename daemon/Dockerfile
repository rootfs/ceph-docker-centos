FROM cephdaemon/base
MAINTAINER Huamin Chen <hchen@redhat.com>

# Add bootstrap script
ADD entrypoint.sh /entrypoint.sh
ADD config.*.sh /

# Add volumes for Ceph config and data
VOLUME ["/etc/ceph","/var/lib/ceph"]

# Execute the entrypoint
WORKDIR /
ENTRYPOINT ["/entrypoint.sh"]