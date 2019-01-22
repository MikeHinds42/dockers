FROM python
LABEL maintainer "Mike Hinds <mike.hinds42@googlemail.com>"

#RUN yum groupinstall -y "X Window System" 
 
RUN useradd -ms /bin/bash developer
  
#RUN mkdir /home/developer/.Idea \
#  && ln -sf /home/developer/.Idea /home/developer/.IdeaIC20
    
WORKDIR /home/developer
USER developer 
ENV HOME /home/developer
CMD /bin/bash