FROM ubuntu
MAINTAINER kohey

RUN apt-get update && apt-get install -y --force-yes libssl0.9.8 curl

RUN curl -L http://toolbelt.treasuredata.com/sh/install-ubuntu-trusty-td-agent2.sh | sh && mkdir -p /var/log/td-agent

ENV GEM_HOME /opt/td-agent/embedded/lib/ruby/gems/2.1.0/
ENV GEM_PATH /opt/td-agent/embedded/lib/ruby/gems/2.1.0/
ENV PATH /opt/td-agent/embedded/bin/:$PATH
ADD ./td-agent.conf /etc/td-agent/td-agent.conf
RUN mkdir -p /var/log
EXPOSE 24224
CMD ["td-agent"]

