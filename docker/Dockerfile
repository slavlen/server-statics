FROM ubuntu:24.04

RUN apt-get update && apt-get install -y \
    openssh-server \
    python3 \
    python3-pip \
    sudo \
    && mkdir /var/run/sshd

RUN mkdir -p /root/.ssh && echo "ssh-rsa AAAA..." > /root/.ssh/authorized_keys \
&& chmod 600 /root/.ssh/authorized_keys \
&& chmod 700 /root/.ssh \
&& chown -R root:root /root/.ssh

CMD ["/usr/sbin/sshd", "-D"]