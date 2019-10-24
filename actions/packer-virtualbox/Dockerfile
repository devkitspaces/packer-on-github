FROM hashicorp/packer:1.4.3

LABEL "com.github.actions.name"="Packer"
LABEL "com.github.actions.description"="Build packer virtualbox images"
LABEL "com.github.actions.icon"="mic"
LABEL "com.github.actions.color"="purple"

LABEL "repository"="http://github.com/jrbeverly/packer-on-github"
LABEL "homepage"="http://github.com/actions"
LABEL "maintainer"="jrbeverly <jonathan@jrbeverly.me>"

RUN apt-get update
RUN apt install -y software-properties-common
RUN wget -q https://www.virtualbox.org/download/oracle_vbox_2016.asc -O- | apt-key add -
RUN wget -q https://www.virtualbox.org/download/oracle_vbox.asc -O- | apt-key add -
RUN apt-get update
RUN apt-get install -y --no-install-recommends virtualbox-5.0
RUN apt-get update 
RUN apt-get install -y make gcc git
