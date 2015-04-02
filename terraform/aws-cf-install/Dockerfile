FROM allomov/terraform:v0.3.6
MAINTAINER Alex Lomov <lomov.as@gmail.com>

RUN sudo apt-get update && sudo apt-get install -y --force-yes ruby-full ntp

RUN git clone https://github.com/cloudfoundry-community/terraform-aws-cf-install.git && \
    cd terraform-aws-cf-install && \
    git reset --hard 26a887f4f3ff6eb47bef555b26ea77f049ded53d

# RUN apt-get install -y --force-yes ssh-import-id
RUN gem install erubis
ADD ssh /root/.ssh
RUN chmod 600 /root/.ssh/*

ADD ./terraform.tfvars.erb /terraform-aws-cf-install/terraform.tfvars.erb
ADD ./deploy-cf /usr/bin/deploy-cf
RUN chmod +x /usr/bin/deploy-cf

# Define default command
CMD ["deploy-cf"]
