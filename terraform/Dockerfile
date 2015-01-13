FROM allomov/ubuntu
MAINTAINER Alex Lomov <lomov.as@gmail.com>

# Install terraform
RUN mkdir /terraform && cd /terraform && \
    wget https://dl.bintray.com/mitchellh/terraform/terraform_0.3.6_linux_amd64.zip && \
    unzip terraform_0.3.6_linux_amd64.zip

ENV PATH $PATH:/terraform

# Define default command
CMD /bin/bash -l
