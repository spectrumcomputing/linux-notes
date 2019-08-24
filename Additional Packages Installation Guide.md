## Additional Packages Installation Guide (Ubuntu 18.04 and later)


### Install required packages

```
sudo apt-get install gnome-tweak-tool arc-theme apt-transport-https ca-certificates curl software-properties-common gcc g++ make chrome-gnome-shell build-essential ubuntu-restricted-extras ttf-mscorefonts-installer ffmpeg neofetch
```
### Replace Snap installed packages so icon themes work
```
sudo snap remove gnome-calculator gnome-characters gnome-logs gnome-system-monitor
sudo apt install gnome-calculator gnome-characters gnome-logs gnome-system-monitor
```

### Papirus Icon Theme

```
sudo add-apt-repository ppa:papirus/papirus  
sudo apt update && sudo apt install papirus-icon-theme  
```

### Docker

```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -  
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable"  
sudo apt-get update  
sudo apt install docker-ce  
sudo usermod -aG docker ${USER}  
su - ${USER}  
docker run hello-world  
```

### NodeJS

```
curl -sL https://deb.nodesource.com/setup_12.x -o nodesource_setup.sh  
sudo bash nodesource_setup.sh  
sudo apt install nodejs  
nodejs -v  
npm -v  
```

### Flatpak (18.04 Only)

```
sudo add-apt-repository ppa:alexlarsson/flatpak  
sudo apt update  
sudo apt install flatpak  
sudo apt install gnome-software-plugin-flatpak  
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.
```

### Celluloid (formerly GNOME MPV) 

As at 13 August the PPA does not seem to have been updated to version 0.17, so I'm including FlatPak instructions too.
```
sudo add-apt-repository ppa:xuzhen666/gnome-mpv
sudo apt-get update
sudo apt-get install gnome-mpv
```
```
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
flatpak install flathub io.github.celluloid_player.Celluloid
```
https://celluloid-player.github.io/installation.html

### Stacer (System Optimizer and Monitor)

```
sudo add-apt-repository ppa:oguzhaninan/stacer -y
sudo apt-get update
sudo apt-get install stacer -y
```

https://github.com/oguzhaninan/Stacer

### Grub Customiser

```
sudo add-apt-repository ppa:danielrichter2007/grub-customizer
sudo apt-get update
sudo apt-get install grub-customizer
```
https://launchpad.net/~danielrichter2007/+archive/ubuntu/grub-customizer

### VMWare Workstation

```
sudo apt-get -y install gcc make linux-headers-$(uname -r) dkms build-essential
```

https://www.vmware.com/uk/products/workstation-pro/workstation-pro-evaluation.html

```
chmod +x VMware*.bundle
sudo ./VMware*.bundle
```
https://linuxconfig.org/install-vmware-tools-on-ubuntu-18-04-bionic-beaver-linux

### Ungroup Utilities on Gnome Desktop
```
gsettings set org.gnome.desktop.app-folders folder-children ['']
```

### Find Windows 10 Product Key
```
sudo cat /sys/firmware/acpi/tables/MSDM | tail -c 32 | xargs -0 echo
```
### Completely remove a package

```
sudo apt-get purge --auto-remove packagename
```
https://askubuntu.com/questions/187888/what-is-the-correct-way-to-completely-remove-an-application

### Convert M4A audio files to MP3

```
ffmpeg -i audio.m4a -acodec libmp3lame -ab 256k audio.mp3
ffmpeg -i audio.m4a -acodec libmp3lame audio.mp3
ffmpeg -v 5 -y -i audio.m4a -acodec libmp3lame -ac 2 -ab 192k audio.mp3
```

### Nutty (A network utility for linux)

    sudo apt-get install libgranite-dev libnotify-dev libxml2-dev libgee-0.8-dev libgtk-3-dev libsqlite3-dev meson valac net-tools nethogs nmap traceroute vnstat curl wireless-tools iproute2 pciutils git build-essential
    
These commands will build Nutty from source:

    git clone https://github.com/babluboy/nutty.git
    cd nutty
    meson build --prefix=/usr
    cd build
    ninja
    
 Then run these commands to install it:
 
     sudo ninja install
     com.github.babluboy.nutty

https://babluboy.github.io/nutty/

### youtube-dl 
Later versions of Ubuntu only ship with Python3 which is called python3 rather than python. This can cause some problems. This method of installation has been tested on Ubuntu 19.04

    sudo curl -L https://yt-dl.org/downloads/latest/youtube-dl -o /usr/local/bin/youtube-dl
    sudo chmod a+rx /usr/local/bin/youtube-dl
    sudo ln -s /usr/bin/python3 /usr/local/bin/python
    
Downloading shows:

Check available video formats with:

    youtube-dl -F URL
    
Download version of your choice:

    youtube-dl -f number URL
    
Download the best quality version (Note that by default youtube-dl tries to download the best available quality):

    youtube-dl URL
    
Check the version:

    youtube-dl --version
    
Upgrade:

    pip install --upgrade youtube_dl

### Useful Links

https://www.omgubuntu.co.uk/2017/05/how-to-update-gnome-extensions

https://extensions.gnome.org/extension/1160/dash-to-panel/

https://extensions.gnome.org/extension/750/openweather/

https://extensions.gnome.org/extension/836/internet-radio/

https://addons.mozilla.org/en-US/firefox/addon/gnome-shell-integration/

https://kb.vmware.com/s/article/1002411

https://askubuntu.com/questions/537787/enable-3d-hw-acceleration-on-vmware-workstation-10-on-ubuntu-14-04

https://odio.io/

https://itsfoss.com/how-to-find-what-devices-are-connected-to-network-in-ubuntu/

https://linoxide.com/linux-how-to/install-use-youtube-dl-ubuntu/

https://github.com/ytdl-org/youtube-dl
