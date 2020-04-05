FROM ubuntu:18.04
ARG START_DIR=/opt/ansible

RUN apt-get update \
 && apt-get install -y software-properties-common python-pip \
 && apt-add-repository -y --update ppa:ansible/ansible \
 && apt-get install -y ansible\
 && pip install ansible[azure] \
 && pip install docker

LABEL "com.azure.dev.pipelines.agent.handler.node.path"="/usr/local/bin/node"

WORKDIR ${START_DIR}

CMD [ "/bin/bash" ]