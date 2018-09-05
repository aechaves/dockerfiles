FROM eclipse/ubuntu_jdk8

ENV CATALINA_HOME=/home/user/tomcat8 \
    ANT_VERSION=1.10.1 \
    ANT_HOME=/home/user/apache-ant

ENV PATH=$ANT_HOME/bin:$PATH

RUN mkdir /home/user/apache-ant && \
    wget -qO- "http://archive.apache.org/dist/ant/binaries/apache-ant-$ANT_VERSION-bin.tar.gz" | tar -zx --strip-components=1 -C /home/user/apache-ant && \
    sudo chgrp -R 0 ${HOME} && \
    sudo chmod -R g+rwX ${HOME}

RUN sudo apt-get -qq update
RUN sudo apt-get -y -q install curl
RUN sudo apt-get -y -q install mercurial
RUN sudo apt-get -y -q install vim
RUN sudo apt-get -y -q install nano