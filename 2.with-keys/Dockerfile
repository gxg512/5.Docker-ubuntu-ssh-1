FROM ubuntu:latest

RUN apt update && apt install  openssh-server sudo -y

#RUN useradd -rm -d /home/ubuntu -s /bin/bash -g root -G sudo -u 1000 test 

#GENERATE A SET OF CREDENTIALS ssh-keygen -f id_rsa

RUN mkdir /root/.ssh && chmod 700 /root/.ssh 
COPY authorized_keys id_rsa id_rsa.pub /root/.ssh/
RUN chmod 600 /root/.ssh/authorized_keys 
RUN chmod 600 /root/.ssh/id_rsa
RUN chmod 644 /root/.ssh/id_rsa.pub 

RUN service ssh start

EXPOSE 22

CMD ["/usr/sbin/sshd","-D"]
