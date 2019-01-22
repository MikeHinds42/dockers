FROM centos
LABEL maintainer "Mike Hinds <mike.hinds42@googlemail.com>"

RUN yum groupinstall -y "X Window System" 


RUN yum install -y wget \
  && mkdir -p /opt/idea \
  && cd /opt/idea \
  && wget http://download.jetbrains.com/idea/ideaIC-2018.3.2.tar.gz -O ./installer.tgz \
  && cd /opt/idea \
  && tar --strip-components=1 -xzf installer.tgz \
  && rm installer.tgz
 
 
RUN useradd -ms /bin/bash developer \
  && mkdir /home/github \
  && chown -R developer.developer /home/github \
  && ln -s /opt/idea/bin/idea.sh /usr/local/bin/idea
 
RUN yum install -y which zenity kde-baseapps xmessage notify-send java emacs xterm

RUN yum install -y https://centos7.iuscommunity.org/ius-release.rpm \
    && yum update -y \
	&& yum install -y python36u python36u-libs python36u-devel python36u-pip git \
	&& ln -s /usr/bin/python3.6 /usr/bin/python3 \
	&& ln -s /usr/bin/pip3.6 /usr/bin/pip3

#RUN mkdir /home/developer/.Idea \
#  && ln -sf /home/developer/.Idea /home/developer/.IdeaIC20
    
WORKDIR /home/developer
USER developer 
ENV HOME /home/developer