FROM ubuntu:14.04

RUN apt-get update
RUN apt-get install -y software-properties-common

# install emacs (eff off, vim users)
RUN apt-get install emacs -y

# install java 8
RUN apt-get update
RUN add-apt-repository ppa:webupd8team/java -y
RUN apt-get update
RUN echo debconf shared/accepted-oracle-license-v1-1 select true | debconf-set-selections
RUN apt-get install oracle-java8-installer -y

# install mercurial
RUN add-apt-repository ppa:mercurial-ppa/releases
RUN apt-get update
RUN apt-get install -y mercurial
RUN apt-get install -y ssh

# install gradle 2.13
RUN add-apt-repository -y ppa:cwchien/gradle
RUN apt-get update
RUN apt-get install -y gradle-2.13

# add 'docker' user
RUN useradd -u 502 -ms /bin/bash docker
USER docker
WORKDIR /home/docker

# download an unpack tomcat 8
ENV TOMCAT_VERSION 8.5.5
RUN wget http://mirrors.koehn.com/apache/tomcat/tomcat-8/v8.5.5/bin/apache-tomcat-${TOMCAT_VERSION}.tar.gz
RUN tar zxvf apache-tomcat-${TOMCAT_VERSION}.tar.gz
ENV CATALINA_HOME /home/docker/apache-tomcat-${TOMCAT_VERSION}