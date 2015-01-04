FROM gliderlabs/alpine:latest
COPY dhcpd.conf /data/
RUN touch /data/dhcpd.leases
VOLUME ["/data"]
