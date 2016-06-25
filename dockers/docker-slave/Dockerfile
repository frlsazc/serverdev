FROM debian:jessie
RUN apt-get update
RUN apt-get install -y openssh-server
RUN apt-get install -y openjdk-7-jre
RUN useradd -m -d /home/jenkins -s /bin/sh jenkins &&\
    echo "jenkins:1234" | chpasswd
RUN sed -i 's|session    required     pam_loginuid.so|session    optional     pam_loginuid.so|g' /etc/pam.d/sshd 
RUN mkdir -p /var/run/sshd
EXPOSE 22
CMD ["/usr/sbin/sshd", "-D"]
