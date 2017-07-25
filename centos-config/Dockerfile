FROM centos
MAINTAINER Jeison Zapata, jeisonz@gco.com.co

ENV JAVA_VERSION 8u45
ENV BUILD_VERSION b13
ENV JAVA_HOME /usr/java/latest

RUN echo 'nameserver 10.66.150.47'>>/etc/resolv.conf

RUN yum -y upgrade

RUN yum -y install wget

RUN wget --no-cookies --no-check-certificate --header "Cookie: oraclelicense=accept-securebackup-cookie" "http://sdlc-esd.oracle.com/ESD6/JSCDL/jdk/8u141-b15/336fa29ff2bb4ef291e347e091f7f4a7/jre-8u141-linux-x64.rpm?GroupName=JSC&FilePath=/ESD6/JSCDL/jdk/8u141-b15/336fa29ff2bb4ef291e347e091f7f4a7/jre-8u141-linux-x64.rpm&BHost=javadl.sun.com&File=jre-8u141-linux-x64.rpm&AuthParam=1500943734_1dc8ee0f56cf9fca2774a3c80c50fda5&ext=.rpm" -O /tmp/jdk-8-linux-x64.rpm

RUN yum -y install /tmp/jdk-8-linux-x64.rpm

RUN alternatives --install /usr/bin/java jar /usr/java/latest/bin/java 200000
RUN alternatives --install /usr/bin/javaws javaws /usr/java/latest/bin/javaws 200000
RUN alternatives --install /usr/bin/javac javac /usr/java/latest/bin/javac 200000

RUN yum update
RUN yum install -y maven
