# Installing z88dk on Ubuntu Linux 20.04 & Fedora 33

## Introduction

This guide is for getting started with installing the z88dk C development suite in Ubuntu 18.04 or 19.04. The target machine here is the Sinclair ZX Spectrum. I'm assuming that you are reasonably proficient in using the command line.

Much of the information I'm using comes from the following two GitHub repositories:

https://github.com/z88dk/z88dk/wiki/installation

https://github.com/z88dk/z88dk/blob/master/doc/ZXSpectrumZSDCCnewlib_01_GettingStarted.md

If you don't already have an emulator installed I reccomend Fuse. 

If you are using Ubuntu then enter the following commands to install it:

    sudo apt-get install fuse-emulator-gtk spectrum-roms 
    
 Fedora instructions to follow
    
## Getting Started with z88dk

Download the latest nightly checked source package and unzip it:

    wget http://nightly.z88dk.org/z88dk-latest.tgz
    tar -xzf z88dk-latest.tgz

This will create a populated z88dk directory in the current working directory.

If you are using Ubuntu you will need the following libraries/packages installed to successfully build z88dk

    sudo apt-get install dos2unix libboost-all-dev texinfo texi2html libxml2-dev subversion bison flex zlib1g-dev
    
If you are using Fedora you will need the following libraries/packages installed to successfully build z88dk
    
    sudo dnf install dos2unix boost-devel texinfo texi2html libxml2-devel subversion bison flex zlib-devel
    
Then enter:

    cd z88dk
    chmod 777 build.sh
    ./build.sh

Supposing you want to keep z88dk in your local user environment, you can configure it permanently in this way:

Start off by using the command `nano ~/.bashrc` to edit your bash profile, then scroll down to the bottom of the file and enter the following commands:
```
export PATH=${PATH}:${HOME}/z88dk/bin
export ZCCCFG=${HOME}/z88dk/lib/config
```   
Finally, save the file with `CTRL + X` and `Y` to confirm changes.  After a reboot it's time to test the installation

The first step is to check that everyone has installed correctly and that the necessary tools are in place. Running each of these commands should produce something similar to the output given:

``` 
peter@ubuntu:~$ zcc
zcc - Frontend for the z88dk Cross-C Compiler - v15100-08748e6-20190811
    
Usage: zcc +[target] {options} {files}
```    
```   
peter@ubuntu:~$ zsdcc -v

ZSDCC IS A MODIFICATION OF SDCC FOR Z88DK
Build: 3.9.1 #11310 (Linux) Aug 11 2019
```
```
peter@ubuntu:~$ z80asm
Z80 Module Assembler 15100-08748e6-20190811
(c) InterLogic 1993-2009, Paulo Custodio 2011-2019
```
```
peter@ubuntu:~$ appmake 
appmake [+target] [options]

The z88dk application generator
```
You should now be able to follow the excellent tutorial on Spectrum C Development which is available here:

https://github.com/z88dk/z88dk/blob/master/doc/ZXSpectrumZSDCCnewlib_01_GettingStarted.md

If you love the ZX Spectrum as much as I do, feel free to visit our website at:

https://spectrumcomputing.co.uk/

We are have a forum which is available here:

https://spectrumcomputing.co.uk/forums
