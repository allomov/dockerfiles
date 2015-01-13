FROM allomov/terraform:v0.3.6
MAINTAINER Alex Lomov <lomov.as@gmail.com>

RUN sudo apt-get update && sudo apt-get install -y --force-yes ruby-full ntp

RUN git clone https://github.com/cloudfoundry-community/terraform-aws-cf-install.git && \
    cd terraform-aws-cf-install && \
    git reset --hard 6883e6ef931d4c2698a1546c4c372e70d5e67ff8

# RUN apt-get install -y --force-yes ssh-import-id
RUN gem install erubis
RUN mkdir ~/.ssh

ADD ./terraform.tfvars.erb /terraform-aws-cf-install/terraform.tfvars.erb
ADD ./deploy-cf /usr/bin/deploy-cf
RUN chmod +x /usr/bin/deploy-cf

ADD ./private-amazon-lomov.pem /root/.ssh/bosh.pem
RUN chmod 700 /root/.ssh/bosh.pem

# Define default command
CMD ["deploy-cf"]
