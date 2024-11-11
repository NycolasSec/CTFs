FROM php:8.3-apache

RUN apt update && apt install ssh -y
RUN mkdir /var/run/sshd
RUN echo "root:P@ssword" | chpasswd
RUN echo 'PermitRootLogin yes' >> /etc/ssh/sshd_config

RUN echo "#!/bin/bash\nservice apache2 start\n/usr/sbin/sshd -D" > /root/init_service.sh
RUN chmod +x /root/init_service.sh


RUN echo "FLAG{SENAI-fbfueblj045hd8}" > /var/www/flag.txt

COPY web /var/www/html/

CMD ["/bin/bash", "-c", "/root/init_service.sh"]
