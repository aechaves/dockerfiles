FROM eclipse/ubuntu_jdk8

ENV CATALINA_HOME=/home/user/tomcat7 \
    ANT_VERSION=1.10.1 \
    ANT_HOME=/home/user/apache-ant

ENV PATH=$ANT_HOME/bin:$PATH

RUN mkdir /home/user/tomcat7 && \
    mkdir /home/user/apache-ant && \
    wget -qO- "http://archive.apache.org/dist/tomcat/tomcat-7/v7.0.79/bin/apache-tomcat-7.0.79.tar.gz" | tar -zx --strip-components=1 -C /home/user/tomcat7 && \
    wget -qO- "http://archive.apache.org/dist/ant/binaries/apache-ant-$ANT_VERSION-bin.tar.gz" | tar -zx --strip-components=1 -C /home/user/apache-ant && \
    rm -rf /home/user/tomcat7/webapps/* && \
    sudo chgrp -R 0 ${HOME} && \
    sudo chmod -R g+rwX ${HOME}

RUN apt-get -qq update
RUN apt-get -y -q install curl
RUN apt-get -y -q install mercurial
RUN apt-get -y -q install vi
RUN apt-get -y -q install nano