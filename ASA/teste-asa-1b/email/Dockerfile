FROM ubuntu:latest

RUN apt update -y

RUN apt upgrade -y

RUN apt install postfix dovecot-imapd dovecot-pop3d telnet -y

COPY main.cf /etc/postfix

COPY start_email.sh /etc/init.d

RUN chmod 755 /etc/init.d/start_email.sh

#portas
EXPOSE 25/TCP
EXPOSE 587/TCP
EXPOSE 110/TCP
EXPOSE 143/TCP

#CMD [ "/usr/sbin/postfix", "start-fg" ]
CMD [ "/etc/init.d/start_email.sh"]

