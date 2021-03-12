FROM ubuntu:20.04

ARG DEBIAN_FRONTEND="noninteractive"
ENV TZ="Asia/Ho_Chi_Minh" 

RUN apt update \
  && apt install -y curl wget vim git net-tools tar systemd sudo zip openssh-server \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/*

ADD bashrc /root/.bashrc

RUN useradd -p '' --create-home --shell /bin/bash -G sudo -u 1000  ubuntu \
  && echo "ubuntu ALL=(root) NOPASSWD:ALL" > /etc/sudoers.d/user && \
    chmod 0440 /etc/sudoers.d/user

ADD --chown=ubuntu:ubuntu bashrc /home/ubuntu/.bashrc

RUN mkdir /home/ubuntu/.ssh \
  && chown ubuntu:ubuntu /home/ubuntu/.ssh

ADD --chown=ubuntu:ubuntu authorized_keys /home/ubuntu/.ssh/authorized_keys

RUN chmod 600 /home/ubuntu/.ssh/authorized_keys \
  && chmod 700 /home/ubuntu/.ssh

COPY docker-entrypoint.sh /docker-entrypoint.sh
RUN chmod +x /docker-entrypoint.sh

USER ubuntu

WORKDIR /home/ubuntu

EXPOSE 22

ENTRYPOINT ["sh", "/docker-entrypoint.sh"]
