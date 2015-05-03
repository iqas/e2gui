## Our buildserver is currently running on: ##

> Ubuntu 12.04.5 LTS (GNU/Linux 3.2.13-grsec-xxxx-grs-ipv6-64 x86_64)

## openplus is build using oe-alliance build-environment and several git repositories: ##

> [https://github.com/oe-alliance/oe-alliance-core](https://github.com/oe-alliance/oe-alliance-core "OE-Alliance")
> 
> [https://github.com/Linux-Box/lbgui.git](https://github.com/Linux-Box/lbgui.git "openplus E2")
> 
> [https://github.com/Linux-Box/MetrixHD.gi](https://github.com/Linux-Box/MetrixHD.gi "openplus Skin")

> and a lot more...


----------

# Building Instructions #

1 - Install packages on your buildserver

    sudo apt-get install -y autoconf automake bison bzip2 chrpath coreutils cvs default-jre default-jre-headless diffstat flex g++ gawk gcc gettext git-core gzip help2man htop info java-common libc6-dev libglib2.0-dev libperl4-corelibs-perl libproc-processtable-perl libtool libxml2-utils make ncdu ncurses-bin ncurses-dev patch perl pkg-config po4a python-setuptools quilt sgmltools-lite sshpass subversion swig tar texi2html texinfo wget xsltproc zip zlib1g-dev

----------
2 - Set your shell to /bin/bash.

    sudo dpkg-reconfigure dash
    When asked: Install dash as /bin/sh?
    select "NO"

----------
3 - Add user openplusbuilder

    sudo adduser openplusbuilder

----------
4 - Switch to user openplusbuilder

    su openplusbuilder

----------
5 - Switch to home of openplusbuilder

    cd ~

----------
6 - Create folder openplus

    mkdir -p ~/openplus

----------
7 - Switch to folder openplus

    cd openplus

----------
8 - Clone oe-alliance git

    git clone git://github.com/oe-alliance/build-enviroment.git

----------
9 - Switch to folder build-enviroment

    cd build-enviroment

----------
10 - Update build-enviroment

    make update

----------
11 - Finally you can start building a image

    make MACHINE=gbquadplus DISTRO=openplus image
