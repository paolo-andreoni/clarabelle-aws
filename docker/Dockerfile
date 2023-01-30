#
# Ansible Dockerfile
#
# https://github.com/dockerfile/ansible
#

# Pull base image.
FROM python:3.11.1-bullseye

# Set user and group
ARG user=ansible
ARG group=ansible
ARG work_path=ansible

RUN apt -y update && \
  apt -y install build-essential \
                 libbz2-dev \
                 libncurses-dev \
                 libffi-dev \
                 libreadline-dev && \
  useradd ${user} && \
  usermod -g sudo ${user};
# libopenssl-dev  libsqlite-dev ;

WORKDIR /${work_path}
COPY ./ /${work_path}/

## Install Ansible python packeges
RUN pip install -U -r requirements.txt;
## Install collection
RUN ansible-galaxy collection install amazon.aws
RUN ansible-galaxy init aws;
#RUN cp ansible/playbook.yml aws/task/main.yaml

#USER ${user}:${group}

## Define default command.
##CMD ["bash"]


