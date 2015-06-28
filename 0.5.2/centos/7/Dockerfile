FROM centos:7

RUN yum install -y unzip

RUN mkdir -p /tmp/consul /ui && \
curl -fL -o consul.zip https://dl.bintray.com/mitchellh/consul/0.5.2_linux_amd64.zip && \
curl -fL -o consul_ui.zip https://dl.bintray.com/mitchellh/consul/0.5.2_web_ui.zip && \
unzip consul.zip -d /usr/local/bin && \
unzip consul_ui.zip -d /ui && \
rm consul.zip consul_ui.zip

VOLUME /tmp/consul

ENTRYPOINT ["consul", "agent", "-data-dir=/tmp/consul", "-ui-dir=/ui"]
