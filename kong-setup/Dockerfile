FROM ubuntu:14.04

RUN apt-get update
RUN apt-get install wget -y
RUN apt-get install emacs -y

RUN apt-get install netcat openssl libpcre3 dnsmasq procps perl -y
RUN wget https://github.com/Mashape/kong/releases/download/0.8.3/kong-0.8.3.trusty_all.deb
RUN dpkg -i kong-0.8.3.*.deb

COPY kong.yml kong.yml