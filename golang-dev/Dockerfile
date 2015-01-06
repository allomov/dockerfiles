FROM allomov/golang
MAINTAINER Alex Lomov <lomov.as@gmail.com>

# Install golang vim extention
RUN cd ~/.vim/bundle && git clone https://github.com/fatih/vim-go.git
RUN echo "Plugin 'fatih/vim-go'" >> ~/.bashrc.local

# Install .direnv
RUN cd /usr/src && git clone http://github.com/zimbatm/direnv && cd direnv && make install
RUN echo '$(direnv hook bash)' >> ~/.bashrc

# Define default command
CMD ["bash"]
