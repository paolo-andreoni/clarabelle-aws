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
  apt -y install sudo && \
  useradd ${user} && \
  usermod -g sudo ${user};


#USER ${user}:${group}

WORKDIR /${work_path}
COPY ./ /${work_path}/

RUN sudo apt -y install build-essential;
#    apt -y install bzip2-devel \
#                   ncurses-devel \
#                   libffi-devel \
#                   readline-devel \
#                   openssl-libs \
#                   sqlite-devel ;

## Install Ansible python packeges
RUN pip install -U -r requirements.txt;
## Install collection
RUN ansible-galaxy collection install amazon.aws



## Define default command.
##CMD ["bash"]


