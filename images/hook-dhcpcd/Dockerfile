FROM --platform=${TARGETARCH} alpine:3.22 AS ethtool

RUN apk add --no-cache ethtool

FROM --platform=${TARGETARCH} linuxkit/dhcpcd:b87e9ececac55a65eaa592f4dd8b4e0c3009afdb

COPY --from=ethtool /usr/sbin/ethtool /usr/sbin/ethtool
COPY --from=ethtool /usr/lib/libmnl.so.0* /usr/lib/
