.. _singularity-installation-label: 

Singularity installation
-------------------------
Firstly, the user needs to install singularity software using the following steps as described in “https://sylabs.io/guides/3.5/user-guide/quick_start.html”, please note some installation requires the user to have sudo rule, if you do not have, please ask your system administrator to install them for you

Install the required packages
=============================

* You need to use these two commands to install the dependency packages:

  ::

    sudo apt-get update
    sudo apt-get install -y \
    build-essential \
    libssl-dev \
    uuid-dev \
    libgpgme11-dev \
    squashfs-tools \
    libseccomp-dev \
    wget \
    pkg-config \
    git \
    cryptsetup

Install go
==========
* This is used by the singularity container

  ::

    export VERSION=1.13 OS=linux ARCH=amd64
    wget https://dl.google.com/go/go$VERSION.$OS-$ARCH.tar.gz
    sudo tar -C /usr/local -xzvf go$VERSION.$OS-$ARCH.tar.gz
    rm go$VERSION.$OS-$ARCH.tar.gz
    sudo ln -s /usr/local/go/bin/go /usr/local/bin/go

* You can test your download by typing

  ::

    go help

Download Singularity from a release
===================================

* The following command should be used to download the code:
  ::

    export VERSION=3.5.2 && wget  https://github.com/sylabs/singularity/releases/download/v${VERSION}/singularity-${VERSION}.tar.gz
    tar -xzf singularity-${VERSION}.tar.gz
    cd singularity

Compile the Singularity source code
====================================

* The code needs to be compiled using the follwing command:
  ::

    ./mconfig
    make -C builddir
    sudo make -C builddir install

* You can test the installation by typing

  ::

    singularity h
