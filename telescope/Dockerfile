FROM centos:latest

ADD mongo.repo /etc/yum.repos.d/
RUN yum -y update && \
yum -y install wget

RUN yum -y install epel-release && yum -y install nodejs npm git mongo-10gen mongo-10gen-server tar && npm install -g meteorite

## Create 'telescope' user
RUN useradd -d /opt/telescope -m telescope

USER telescope
WORKDIR /opt/telescope 
RUN curl https://install.meteor.com | /bin/sh
RUN git clone https://github.com/TelescopeJS/Telescope.git
WORKDIR /opt/telescope/Telescope
RUN /opt/telescope/.meteor/meteor add accounts-google
ADD run.sh /opt/telescope/Telescope/bin/run.sh

USER root
RUN chmod +x /opt/telescope/Telescope/bin/run.sh

USER telescope
EXPOSE 3000
CMD ["/opt/telescope/Telescope/bin/run.sh"]
