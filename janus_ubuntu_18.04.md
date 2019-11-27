1. sudo apt-get install libmicrohttpd-dev libjansson-dev libnice-dev libssl-dev libsrtp-dev libsofia-sip-ua-dev libglib2.0-dev libopus-dev libogg-dev libcurl4-openssl-dev pkg-config gengetopt libtool automake gtk-doc-tools autoconf autogen gcc g++ libconfig++-dev doxygen graphviz cmake

2. git clone https://gitlab.freedesktop.org/libnice/libnice
    cd libnice
    ./autogen.sh
    ./configure --prefix=/usr
    make && sudo make install

3.  git clone https://github.com/warmcat/libwebsockets.git
    cd libwebsockets
    mkdir build
    cd build
    cmake -DCMAKE_INSTALL_PREFIX:PATH=/usr -DCMAKE_C_FLAGS="-fpic" ..
    make && sudo make install

4.  wget https://nodejs.org/dist/v13.2.0/node-v13.2.0-linux-x64.tar.xz
    sudo mkdir -p /usr/local/lib/nodejs
    sudo tar -xJvf node-v13.2.0-linux-x64.tar.xz -C /usr/local/lib/nodejs 
    sudo nano ~/.profile
        export PATH=/usr/local/lib/nodejs/node-v13.2.0-linux-x64/bin:$PATH
        . ~/.profile

 
5.  sudo npm -g install http-server

6.  wget https://github.com/cisco/libsrtp/archive/v2.1.0.tar.gz
    tar xfv v2.1.0.tar.gz
    cd libsrtp-2.1.0
    ./configure --prefix=/usr --enable-openssl
    make shared_library && sudo make install
    
8.  wget https://github.com/sctplab/usrsctp/archive/0.9.3.0.tar.gz
    tar zxvf 0.9.3.0.tar.gz 
    cd usrsctp-0.9.3.0/
    ./bootstrap
    ./configure
    make
    sudo make install
    

7.  wget https://github.com/meetecho/janus-gateway/archive/v0.7.6.tar.gz
    tar xzfv v0.7.6.tar.gz 
    cd janus-gateway-0.7.6/
    sh autogen.sh
    ./configure --prefix=/opt/janus --enable-websockets --enable-docs
    make
    sudo make install
    sudo make configs

8.  /opt/node-v11.10.1-linux-x64/bin/http-server

9.  /opt/janus/bin/janus --debug-level=7 --log-file=$HOME/janus-log
