# VERSION 2.0.0
# AUTHOR:         Nicolas Lamirault <nicolas.lamirault@gmail.com>
# DESCRIPTION:    zeiot/rpi-helm

FROM resin/armv7hf-debian:jessie
MAINTAINER Nicolas Lamirault <nicolas.lamirault@gmail.com>

ENV HELM_VERSION 2.0.0

# ENV GOARM=7 \
#     GOARCH=arm \
#     GOPATH=/go

# RUN apt-get update && \
#     apt-get install -y git mercurial build-essential wget ca-certificates libssl-dev curl --no-install-recommends

# ADD http://resin-packages.s3.amazonaws.com/golang/v1.7.4/go1.7.4.linux-armv7hf.tar.gz /go.tar.gz
# RUN mkdir -p /usr/local/go /go && \
#     tar -xzf /go.tar.gz -C /usr/local/go --strip-components=1 && \
#     rm -f /go.tar.gz

# ENV GOROOT /usr/local/go
# ENV PATH $GOPATH/bin:/usr/local/go/bin:$PATH

# ADD https://github.com/kubernetes/helm/archive/v${HELM_VERSION}.tar.gz /helm.tar.gz
# RUN echo $PATH
# RUN mkdir -p $GOPATH/src/k8s.io/helm && \
#     tar -xzf /helm.tar.gz -C $GOPATH/src/k8s.io/helm/ --strip-components=1 && \
#     rm -f /helm.tar.gz
# RUN PATH=$PATH GOPATH=$GOPATH GOARM=$GOARM GOARCH=$GOARCH go get -u github.com/Masterminds/glide
# RUN cd $GOPATH/src/k8s.io/helm && \
#     glide install --strip-vendor --strip-vcs && \
#     PATH=$PATH GOARM=$GOARM GOARCH=$GOARCH GOOS=linux make build

# ADD https://github.com/Masterminds/glide/releases/download/v0.12.3/glide-v0.12.3-linux-armv7.tar.gz /glide.tar.gz
# RUN tar zxvf /glide.tar.gz && \
#     mv /linux-armv7/glide /usr/local/bin/glide

# RUN mkdir -p ${GOPATH}/src/k8s.io && \
#     git clone https://github.com/kubernetes/helm.git ${GOPATH}/src/k8s.io/helm
# RUN cd $GOPATH/src/k8s.io/helm && /usr/bin/git checkout v${HELM_VERSION}
# # RUN GOPATH=${GOPATH} GOARM=${GOARM} GOARCH=${GOARCH} go get -u github.com/Masterminds/glide
# RUN GOPATH=${GOPATH} GOARM=${GOARM} GOARCH=${GOARCH} go get -u github.com/mitchellh/gox
# RUN GOPATH=${GOPATH} GOARM=${GOARM} GOARCH=${GOARCH} glide install --strip-vendor --strip-vcs
# RUN cd $GOPATH/src/k8s.io/helm && GOPATH=${GOPATH} GOARM=${GOARM} GOARCH=${GOARCH} make build
# RUN rm -rf /tmp/* /var/tmp/* /var/cache/apk/* && \
#     cp /go/src/k8s.io/helm/bin/* / && \
#     rm -rf ${GOPATH}

COPY ./helm-v2.0.0-linux-arm.tar.gz /helm.tar.gz
RUN mkdir -p /usr/local/helm && \
    tar -xzf /helm.tar.gz -C /usr/local/helm --strip-components=1 && \
    mv /usr/local/helm/tiller /tiller && \
    rm -f /helm.tar.gz

RUN chmod +x /tiller

EXPOSE 44134

ENTRYPOINT [ "/tiller" ]

CMD ["/tiller"]
