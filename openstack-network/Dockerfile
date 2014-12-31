FROM bradlaue/centos-systemd
COPY config /config
COPY network-node-2-nic.sh /network-node-2-nic.sh
COPY make-network.sh /make-network.sh
RUN yum -y reinstall dbus
CMD ["/usr/sbin/init"]
