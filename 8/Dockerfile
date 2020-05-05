FROM registry.centos.org/centos/centos:8

ENV NAME=centos-toolbox VERSION=8
LABEL com.github.containers.toolbox="true" \
    com.github.debarshiray.toolbox="true" \
    com.redhat.component="$NAME" \
    name="$FGC/$NAME" \
    version="$VERSION" \
    usage="This image is meant to be used with the toolbox command" \
    summary="Base image for creating CentOS toolbox containers" \
    maintainer="Link Dupont <linkdupont@fedoraproject.org>"

COPY README.md /

RUN sed -i '/tsflags=nodocs/d' /etc/dnf/dnf.conf

COPY missing-docs /
RUN dnf -y reinstall $(<missing-docs)
RUN rm /missing-docs

COPY extra-packages /
RUN dnf -y install $(<extra-packages)
RUN rm /extra-packages

RUN dnf clean all

CMD /bin/sh
