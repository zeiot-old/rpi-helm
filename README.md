# RPI Helm

* Master : [![Circle CI](https://circleci.com/gh/zeiot/rpi-helm/tree/master.svg?style=svg)](https://circleci.com/gh/zeiot/rpi-helm/tree/master) [![Build Status](https://travis-ci.org/zeiot/rpi-helm.svg?branch=master)](https://travis-ci.org/zeiot/rpi-helm)
* Develop : [![Circle CI](https://circleci.com/gh/zeiot/rpi-helm/tree/develop.svg?style=svg)](https://circleci.com/gh/zeiot/rpi-helm/tree/develop) [![Build Status](https://travis-ci.org/zeiot/rpi-helm.svg?branch=develop)](https://travis-ci.org/zeiot/rpi-helm)

Docker image of [Helm][] to use on a [Raspberry PI][].

Configure binfmt-support on the Docker host (works locally or remotely, i.e: using boot2docker):

    $ docker run --rm --privileged multiarch/qemu-user-static:register --reset

Then you can run an armhf image from your x86_64 Docker host :

    $ make run version=x.x

Or build :

    $ make build version=x.x


## Usage


    $ docker run zeiot/rpi-helm:2.1.0 --help
    The Kubernetes Helm server.

    Tiller is the server for Helm. It provides in-cluster resource management.

    By default, Tiller listens for gRPC connections on port 44134.

    Usage:
        tiller [flags]

    Flags:
        -l, --listen string    address:port to listen on (default ":44134")
            --storage string   storage driver to use. One of 'configmap' or 'memory' (default "configmap")
            --trace            enable rpc tracing



# Supported tags

* [![](https://images.microbadger.com/badges/version/zeiot/rpi-helm:2.1.0.svg)](http://microbadger.com/images/zeiot/rpi-helm:2.1.0 "Get your own version badge on microbadger.com")
* [![](https://images.microbadger.com/badges/version/zeiot/rpi-helm:2.0.0.svg)](http://microbadger.com/images/zeiot/rpi-helm:2.0.0 "Get your own version badge on microbadger.com")


## License

See [LICENSE](LICENSE) for the complete license.


## Changelog

A [ChangeLog.md](ChangeLog.md) is available.


## Contact

Nicolas Lamirault <nicolas.lamirault@gmail.com>


[Raspberry PI]: https://www.raspberrypi.org/
[Helm]: https://github.com/kubernetes/helm
