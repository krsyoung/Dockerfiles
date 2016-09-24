FROM ubuntu:16.04
MAINTAINER Christopher Young "krsyoung@gmail.com"

# update / install packages
RUN apt-get update && \
  apt-get install -y apt-transport-https ca-certificates curl git && \
  apt-key adv --keyserver hkp://p80.pool.sks-keyservers.net:80 --recv-keys 58118E89F3A912897C070ADBF76221572C52609D && \
  apt-get clean && \
  rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# set-up Docker sources
RUN echo 'deb https://apt.dockerproject.org/repo ubuntu-xenial main' > /etc/apt/sources.list.d/docker.list

# install Docker Engine
RUN apt-get update && \
  apt-get purge lxc-docker && \
  apt-cache policy docker-engine && \
  # apt-get install linux-image-extra-$(uname -r) linux-image-extra-virtual && \
  apt-get install -y docker-engine

# start Docker Engine
RUN service docker start

# install docker-compose
# https://github.com/docker/compose/releases
RUN curl -L https://github.com/docker/compose/releases/download/1.8.1/docker-compose-`uname -s`-`uname -m` > /usr/local/bin/docker-compose && \
chmod +x /usr/local/bin/docker-compose

# install docker-machine
# https://github.com/docker/machine/releases/
RUN curl -L https://github.com/docker/machine/releases/download/v0.8.1/docker-machine-`uname -s`-`uname -m` >/usr/local/bin/docker-machine && \
chmod +x /usr/local/bin/docker-machine

# install cloud foundry CLI
# https://github.com/cloudfoundry/cli#downloads
RUN curl -Lo /tmp/cf-cli.deb 'https://cli.run.pivotal.io/stable?release=debian64&version=6.22.1&source=github-rel' && \
dpkg -i /tmp/cf-cli.deb && apt-get install -f

# install IBM Containers CF plugin
# https://console.ng.bluemix.net/docs/containers/container_cli_cfic.html
RUN cf install-plugin -f https://static-ice.ng.bluemix.net/ibm-containers-linux_x64

# bash it up
CMD ["bash"]
