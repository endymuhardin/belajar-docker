FROM maven:latest

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update \
    && apt-get install -y mysql-server \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* \ 
    && /etc/init.d/mysql start \
    && echo "grant all on belajar.* to belajar@localhost identified by 'java'" | mysql -uroot \
    && echo "drop database if exists belajar" | mysql -uroot \
    && echo "create database belajar" | mysql -uroot

RUN systemctl enable mysql.service
VOLUME ~/.m2 /var/lib/mysql /tmp
ENTRYPOINT service mysql start && /bin/bash
