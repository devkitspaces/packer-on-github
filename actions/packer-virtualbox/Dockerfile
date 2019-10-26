FROM partlab/ubuntu-golang:latest
ENV PACKER_DEV=1

LABEL "com.github.actions.name"="Packer"
LABEL "com.github.actions.description"="Build images with packer"
LABEL "com.github.actions.icon"="mic"
LABEL "com.github.actions.color"="purple"

LABEL "repository"="http://github.com/jrbeverly/packer-on-github"
LABEL "homepage"="http://github.com/actions"
LABEL "maintainer"="jrbeverly <jonathan@jrbeverly.me>"

RUN apt-get update
RUN apt-get install -y git bash openssl
RUN go get github.com/mitchellh/gox
RUN go get github.com/hashicorp/packer

WORKDIR $GOPATH/src/github.com/hashicorp/packer

RUN /bin/bash scripts/build.sh

RUN add-apt-repository multiverse 
RUN apt-get update
RUN apt install -y virtualbox

WORKDIR $GOPATH
ENTRYPOINT ["bin/packer"]