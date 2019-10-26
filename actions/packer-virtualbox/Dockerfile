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
RUN apt-get install -y git bash openssl curl zip
RUN curl -SL https://releases.hashicorp.com/packer/1.4.2/packer_1.4.2_linux_amd64.zip -o packer_1.4.2_linux_amd64.zip
RUN unzip packer_1.4.2_linux_amd64.zip
RUN mv packer /usr/bin/packer

RUN add-apt-repository multiverse 
RUN apt-get update
RUN apt install -y virtualbox

WORKDIR $GOPATH
ENTRYPOINT ["bin/packer"]