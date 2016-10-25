# IBM Containers CI

This Docker image provides all of the tools necessary to interact with the
[IBM Bluemix](http://bluemix.net) platform.

The following components are included in the image:

* Docker Engine
* docker-machine
* docker-compose
* CloudFoundry CLI
* IBM Container CloudFoundry plugin for [IBM Containers](https://console.ng.bluemix.net/docs/containers/container_index.html)
* IBM OpenWhisk CLI for [IBM OpenWhisk](https://developer.ibm.com/openwhisk/)


## Development

Build the image:

    docker build -t ibm-containers-ci:latest .

Run the image:

    docker run -it --rm ibm-containers-ci:latest
