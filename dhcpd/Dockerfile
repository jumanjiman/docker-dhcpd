FROM fedora:latest
RUN yum -y update; yum clean all
RUN yum -y install dhcp; yum clean all

# grep -i dhcp /etc/services | grep -v qip | awk '{print "EXPOSE", $2}'
EXPOSE 68/tcp
EXPOSE 68/udp
EXPOSE 546/tcp
EXPOSE 546/udp
EXPOSE 547/tcp
EXPOSE 547/udp
EXPOSE 647/tcp
EXPOSE 647/udp
EXPOSE 847/tcp
EXPOSE 847/udp

# This one is not in /etc/services, but it's pretty important.
EXPOSE 67/tcp
EXPOSE 67/udp

ENTRYPOINT ["/usr/sbin/dhcpd"]
CMD ["-4", "-f", "-d", "-cf", "/data/dhcpd.conf", "-lf", "/data/dhcpd.leases", "-pf", "/dev/null"]
