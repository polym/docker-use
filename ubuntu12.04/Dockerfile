# sshd
#
# VERSION               0.0.1

FROM     ubuntu:12.04
MAINTAINER hongbo.mo "hongbo.mo@upai.com"

RUN sed -i 's/archive.ubuntu.com/mirrors.163.com/' /etc/apt/sources.list

RUN apt-get update && apt-get install -y openssh-server g++ make curl
RUN mkdir /var/run/sshd
RUN echo 'root:root' | chpasswd
RUN sed -i 's/PermitRootLogin without-password/PermitRootLogin yes/' /etc/ssh/sshd_config

RUN mkdir -p /root/.ssh/
ADD .ssh/id_rsa /root/.ssh/
ADD .ssh/id_rsa.pub /root/.ssh/

EXPOSE 22
EXPOSE 1001
EXPOSE 1002
EXPOSE 1003
EXPOSE 1004
EXPOSE 1005
EXPOSE 1006
CMD ["/usr/sbin/sshd", "-D"]
