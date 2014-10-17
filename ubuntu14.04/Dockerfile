# sshd
#
# VERSION               0.0.1

FROM     ubuntu:14.04
MAINTAINER hongbo.mo "hongbo.mo@upai.com"

RUN sed -i 's/archive.ubuntu.com/mirrors.163.com/' /etc/apt/sources.list

# basic software
RUN apt-get update && apt-get install -y openssh-server g++ make vim screen
RUN mkdir /var/run/sshd
RUN echo 'root:root' | chpasswd
RUN sed -i 's/PermitRootLogin without-password/PermitRootLogin yes/' /etc/ssh/sshd_config

EXPOSE 22
CMD ["/usr/sbin/sshd", "-D"]
