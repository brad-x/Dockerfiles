FROM bradlaue/centos-systemd
COPY config /config
COPY ipsetup.sh /ipsetup.sh
COPY controller-node.sh /controller-node.sh
RUN yum -y reinstall dbus
CMD ["/usr/sbin/init"]
