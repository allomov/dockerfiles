FROM allomov/ubuntu
RUN apt-get update 

RUN apt-get -y update 
RUN apt-get -y install git git-core curl gawk g++ gcc make libc6-dev libreadline6-dev \  
    zlib1g-dev libssl-dev libyaml-dev libsqlite3-dev sqlite3 autoconf \  
    libgdbm-dev libncurses5-dev automake libtool bison pkg-config libffi-dev

RUN apt-get install -y postgresql postgresql-contrib postgresql-client libpq5 libpq-dev

RUN wget http://ftp.ruby-lang.org/pub/ruby/ruby-2.1.5.tar.gz
RUN tar -xzvf ruby-2.1.5.tar.gz
RUN cd ruby-2.1.5 && ./configure && make && sudo make install
RUN gem install bundler --no-ri --no-rdoc

RUN apt-get install -y nodejs npm  
RUN ln -s  /usr/bin/nodejs  /usr/bin/node 
