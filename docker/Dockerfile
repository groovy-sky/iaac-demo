FROM ubuntu:18.04
ARG START_DIR=/opt/automation

COPY ${GITHUB_WORKSPACE} ${START_DIR}

RUN apt-get update \
 && apt-get install -y software-properties-common python-pip curl nodejs \
 && apt-add-repository -y --update ppa:ansible/ansible \
 && apt-get install -y ansible\
 && pip install ansible[azure] \
 && pip install docker

LABEL "com.azure.dev.pipelines.agent.handler.node.path"="/usr/bin/node"

WORKDIR ${START_DIR}

CMD [ "/bin/bash" ]