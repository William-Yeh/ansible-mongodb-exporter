# building linux-amd64 native binary via Dockerized Go compiler
#
# @see https://registry.hub.docker.com/_/golang/
#

# pull base image
FROM golang:1.6.2
MAINTAINER William Yeh <william.pjyeh@gmail.com>


ENV PROJECT_REPO  github.com/dcu/mongodb_exporter
ENV EXE_NAME      mongodb_exporter-linux-amd64

ENV GOPATH        /opt
ENV PATH          $GOPATH/bin:$PATH
WORKDIR           /opt

RUN echo "===> Fetch and build main project..."
RUN go get -u $PROJECT_REPO
RUN cd /opt/src/$PROJECT_REPO  && \
    make build


# copy executable...
RUN      mkdir -p /dist
VOLUME   [ "/dist" ]
CMD      cp  $GOPATH/src/$PROJECT_REPO/mongodb_exporter  /dist/$EXE_NAME
