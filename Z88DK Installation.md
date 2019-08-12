# Installing z88dk on Ubuntu Linux 18.04, 18.10 or 19.04

## Introduction

This guide is for getting started with installing the z88dk C development suite in Ubuntu 18.04 or 19.04.  I'm assuming that you are reasonably proficient in using the command line.

Much of the information I'm using comes from the following two GitHub repositories:

https://github.com/z88dk/z88dk/wiki/installation

https://github.com/z88dk/z88dk/blob/master/doc/ZXSpectrumZSDCCnewlib_01_GettingStarted.md

If you don't already have an emulator installed I reccomend Fuse. From the command line, enter the following commands to install it:

    sudo apt-get install fuse-emulator-gtk spectrum-roms
    
Sometimes the versions of Fuse in the Ubuntu repositories are out of date.  If you want to make sure you have the latest version you can use FlatPak and install Fuse from here:

https://flathub.org/apps/details/net.sf.fuse_emulator

Ubuntu 18.04 does not have FlatPak installed by default, but it can easily be installed by using the following commands:
``` 
sudo add-apt-repository ppa:alexlarsson/flatpak  
sudo apt update  
sudo apt install flatpak  
sudo apt install gnome-software-plugin-flatpak  
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub
``` 

Once you have rebooted you can install Fuse using:

    flatpak install flathub net.sf.fuse_emulator
## Getting Started with z88dk

Download the latest nightly checked source package and unzip it:

    wget http://nightly.z88dk.org/z88dk-latest.tgz
    tar -xzf z88dk-latest.tgz

This will create a populated z88dk directory in the current working directory.

You will need the following libraries/packages installed to successfully build z88dk:

    sudo apt-get install dos2unix libboost-all-dev texinfo texi2html libxml2-dev subversion bison flex zlib1g-dev
    sudo apt-get install zlib1g-dev
    
Then enter:

    cd z88dk
    chmod 777 build.sh
    ./build.sh

Supposing you want to keep z88dk in your local user environment (AKA 'home directory'), you can configure it permanently in this way:

Start off by using the command `nano ~/.bashrc` to edit your bash profile, then scroll down to the bottom of the file and enter the following commands:
```
export PATH=${PATH}:${HOME}/z88dk/bin
export ZCCCFG=${HOME}/z88dk/lib/config
```   
Finally, save the file with `CTRL + X` and `Y` to confirm changes.  After a reboot it's time to test the installation

The first step is to check the necessary tools are in place. Running each of these commands should produce something similar to the output given:

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
https://spectrumcomputing.co.uk/forums
