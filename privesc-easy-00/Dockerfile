FROM ubuntu:latest

RUN apt update
RUN apt install sudo ssh vim apache2  -y
RUN mkdir /var/run/sshd

RUN useradd -m dev_web
RUN useradd -m dev_db

RUN echo "root:P@ssword" | chpasswd
RUN echo "dev_web:dev" | chpasswd
RUN echo "dev_db:superdb" | chpasswd

RUN echo "dev_db ALL=(ALL:ALL) /usr/bin/vim" >> /etc/sudoers

RUN echo "{\n\tuser:'dev_db',\n\tpassword: 'superdb'\n}" > /var/www/credentials.json
RUN echo "FLAG{SENAI-gj4ns02n47fbj305}" > /root/flag.txt


CMD ["/bin/bash", "-c", "/usr/sbin/sshd -D"]
