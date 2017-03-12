# VERSION 2.2.0
# AUTHOR:         Nicolas Lamirault <nicolas.lamirault@gmail.com>
# DESCRIPTION:    zeiot/rpi-helm

FROM resin/armv7hf-debian:jessie
MAINTAINER Nicolas Lamirault <nicolas.lamirault@gmail.com>

ENV HELM_VERSION 2.2.0

COPY ./helm-v2.2.0-linux-arm.tar.gz /helm.tar.gz
RUN mkdir -p /usr/local/helm && \
    tar -xzf /helm.tar.gz -C /usr/local/helm --strip-components=1 && \
    mv /usr/local/helm/tiller /tiller && \
    rm -f /helm.tar.gz

RUN chmod +x /tiller

EXPOSE 44134

ENTRYPOINT [ "/tiller" ]

CMD ["/tiller"]
