# Dockerfile is the configuration file used to build a Docker image
# custom your username and password

 # setting base image
FROM debian

 # new a directory for sshd to run
RUN mkdir -p /var/run/sshd

 # installing ssh server
RUN apt-get update
RUN apt-get install -y openssh-server

 # installing sudo
RUN apt-get install -y sudo

 # make ssh services use IPv4 to let X11 forwarding work correctly
RUN echo AddressFamily inet >> /etc/ssh/sshd_config

 # defining user account imformation
ARG username=ics
ARG userpasswd=ics

 # adding user
RUN useradd -ms /bin/bash vyckey && (echo vyckey:vyckey213 | chpasswd)

 # adding user to sudo group
RUN adduser vyckey sudo

 # setting running application
CMD /usr/sbin/sshd -D
