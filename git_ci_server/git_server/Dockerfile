From ubuntu:18.04
Run apt-get update && \
	apt-get install -y sudo && \
	apt-get install -y apt-utils && \
	apt-get install -y software-properties-common && \
	apt-get install -y vim && \
    apt-get install -y git && \
    apt-get install -y openssh-client && \ 
	apt-get install -y zip unzip	
RUN ssh-keygen -q -t rsa -N '' -f /root/.ssh/id_rsa
RUN apt-get install -y openssh-server
RUN apt-get install -y netcat ssh iputils-ping
RUN mkdir /var/run/sshd && \
    chmod 0755 /var/run/sshd
# RUN useradd -p $(openssl passwd -1 u2password) --create-home --shell /bin/bash --groups sudo u2
EXPOSE 80
EXPOSE 22
CMD ["/usr/sbin/sshd", “-D”]