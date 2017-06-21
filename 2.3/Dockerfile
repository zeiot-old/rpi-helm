# VERSION 2.3.1
# AUTHOR:         Nicolas Lamirault <nicolas.lamirault@gmail.com>
# DESCRIPTION:    zeiot/rpi-helm

FROM resin/armv7hf-debian:stretch
MAINTAINER Nicolas Lamirault <nicolas.lamirault@gmail.com>

ENV HELM_VERSION 2.3.1

COPY ./helm-v${HELM_VERSION}-linux-arm.tar.gz /helm.tar.gz
RUN mkdir -p /usr/local/helm && \
    tar -xzf /helm.tar.gz -C /usr/local/helm --strip-components=1 && \
    mv /usr/local/helm/tiller /tiller && \
    rm -f /helm.tar.gz

RUN chmod +x /tiller

EXPOSE 44134

ENTRYPOINT [ "/tiller" ]

CMD ["/tiller"]
