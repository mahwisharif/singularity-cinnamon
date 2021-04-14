BootStrap:debootstrap 
OSVersion: xenial
MirrorURL:  http://us.archive.ubuntu.com/ubuntu/

%runscript
    echo "going to set up and install - please wait"
    echo "This is what happens when you run the container..."
    lsb_release -a
    echo "checking cmake version..."
    cmake --version
    echo "checking make version..."
    make --version
    echo "checking gcc version..."
    gcc --version
    echo "checking clang version..."
    clang --version
    echo "checking bison version..."
    bison --version
    echo "checking clang version"
%post
    apt-get install -y software-properties-common
    add-apt-repository universe
    apt-get update
    apt-get -y install sudo 
    apt-get -y install build-essential curl git man wget vim autoconf libtool bison flex cmake clang-3.8 libelf-dev libboost-all-dev libdwarf-dev zlib1g-dev libtbb-dev binutils-dev libiberty-dev
    apt -y install python
    apt-get clean
    git clone https://github.com/mahwisharif/Janus.git
    cd Janus
    git checkout -b cinnamon origin/cinnamon
    cd ..
    wget https://software.intel.com/sites/landingpage/pintool/downloads/pin-3.13-98189-g60a6ef199-gcc-linux.tar.gz
    mkdir pin-3.13 && tar xvzf pin-3.13-98189-g60a6ef199-gcc-linux.tar.gz --strip-components 1
    git clone https://github.com/mahwisharif/pin-cinnamon
    cp -r pin-cinnamon/MyDSLTool pin-3.13/source/tools/

%help

%test
 
%environment

