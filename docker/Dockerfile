#
# Ansible Dockerfile
#
# https://github.com/dockerfile/ansible
#

# Pull base image.
FROM python:3.11.1-bullseye


WORKDIR /data
COPY ./ /data/

## Images from oraclelinux:9
RUN apt -y update && \
    apt -y groupinstall "Development Tools";
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


