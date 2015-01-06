FROM ubuntu:trusty
MAINTAINER Alex Lomov <lomov.as@gmail.com>

# Install utilities
RUN locale-gen en_US.UTF-8 && \
    echo 'LANG="en_US.UTF-8"' > /etc/default/locale && \
    sed -i 's/# \(.*multiverse$\)/\1/g' /etc/apt/sources.list && \
    apt-get update && \
    apt-get install -y --force-yes \
    build-essential software-properties-common \
    apt-transport-https curl bash-completion \
    wget git unzip pwgen mc vim emacs
    

RUN curl http://j.mp/spf13-vim3 -L -o - | sh
# RUN curl -L http://git.io/epre | sh   # install prelude for emacs

# install dotfiles
RUN cd ~ && git clone https://github.com/allomov/dotfiles.git          && \
    echo 'source ~/dotfiles/bash/env'               >> ~/.bash_profile && \
    echo 'source ~/dotfiles/bash/aliases'           >> ~/.bash_profile && \
    echo 'source ~/dotfiles/bash/config'            >> ~/.bash_profile && \
    echo 'source /etc/bash_completion.d/git-prompt' >> ~/.bash_profile && \
    echo 'source ~/.bash_profile'                   >> ~/.bashrc



# Define default command
CMD /bin/bash -l
