# Installing z88dk on Ubuntu Linux 18.04 or 19.04

Download the latest nightly checked source package and unzip it:

    wget http://nightly.z88dk.org/z88dk-latest.tgz
    tar -xzf z88dk-latest.tgz

This will create a populated z88dk directory in the current working directory.

You will need the following libraries/packages installed to successfully build z88dk:

    sudo apt-get install dos2unix libboost-all-dev texinfo texi2html libxml2-dev subversion bison flex
    sudo apt-get install zlib1g-dev
    
Then enter:

    cd z88dk
    chmod 777 build.sh
    ./build.sh

Supposing you want to keep z88dk in your local user environment (AKA 'home directory'), you can configure it permanently in this way:

Start of by entering `nano ~/.bash_profile` to edit your bash profile, then enter in the following:

    export PATH=${PATH}:${HOME}/z88dk/bin
    export ZCCCFG=${HOME}/z88dk/lib/config
