FROM ubuntu:latest

RUN apt update -y

RUN apt upgrade -y

RUN apt install bind9 bind9-utils dnsutils nano -y

COPY named.conf /etc/bind/named.conf

COPY named.conf.local /etc/bind/named.conf.local

COPY db.es.br /etc/bind/db.es.br
COPY db.rv.es.br /etc/bind/db.rv.es.br


EXPOSE 53/tcp
EXPOSE 53/UDP
EXPOSE 953/TCP

CMD [ "/usr/sbin/named", "-g", "-c", "/etc/bind/named.conf", "-u", "bind" ]

