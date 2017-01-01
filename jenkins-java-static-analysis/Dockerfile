FROM jenkins:2.32.1

ENV JAVA_HOME /opt/jdk/jdk1.8.0_111

USER root

# Install Oracle JDK http://askubuntu.com/questions/536134/install-specific-java-version-for-12-04/536161#536161
RUN mkdir /opt/jdk
RUN cd /opt
RUN wget --header "Cookie: oraclelicense=accept-securebackup-cookie" http://download.oracle.com/otn-pub/java/jdk/8u111-b14/jdk-8u111-linux-x64.tar.gz -O /tmp/jdk-8u111-linux-64.tar.gz
RUN tar -zxf /tmp/jdk-8u111-linux-64.tar.gz -C /opt/jdk

# Timezone 보정 : http://serverfault.com/questions/683605/docker-container-time-timezone-will-not-reflect-changes
ENV TZ=Asia/Seoul
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

# projects
RUN mkdir /projects
RUN chown -R jenkins:jenkins /projects

COPY executors.groovy /usr/share/jenkins/ref/init.groovy.d/executors.groovy
COPY plugins.txt /usr/share/jenkins/plugins.txt
RUN /usr/local/bin/plugins.sh /usr/share/jenkins/plugins.txt

# 기본 Job 복제
ADD /ref /usr/share/jenkins/ref

USER jenkins

VOLUME /projects
