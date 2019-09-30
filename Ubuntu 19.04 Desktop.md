## Ubuntu 19.04 Additional Packages Installation Notes

You are advised not to copy and paste commands without knowing what they do.  There are links to more information throughout this document to additional information


### Install required packages

```
sudo apt-get install gnome-tweak-tool apt-transport-https ca-certificates curl software-properties-common gcc g++ make chrome-gnome-shell build-essential ubuntu-restricted-extras ttf-mscorefonts-installer arc-theme ffmpeg
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
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu disco stable"  
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
### Flatpak

```
sudo apt install flatpak  
sudo apt install gnome-software-plugin-flatpak  
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```
https://flathub.org/home

### Celluloid (formerly GNOME MPV) Flatpak

```
flatpak install flathub io.github.celluloid_player.Celluloid
```
https://celluloid-player.github.io/installation.html

### Filezilla Flatpak
FileZilla Client is a fast and reliable cross-platform FTP, FTPS and SFTP client with lots of useful features and an intuitive graphical user interface

```
flatpak install flathub org.filezillaproject.Filezilla
```
https://flathub.org/apps/details/org.filezillaproject.Filezilla

### Evolution Flatpak
Manage your email, contacts and schedule

```
flatpak install flathub org.gnome.Evolution
```
https://flathub.org/apps/details/org.gnome.Evolution

### Spotify Flatpak
Online music streaming service

```
flatpak install flathub com.spotify.Client
```
https://flathub.org/apps/details/com.spotify.Client


### Stacer (System Optimizer and Monitor)

```
sudo add-apt-repository ppa:oguzhaninan/stacer -y
sudo apt-get update
sudo apt-get install stacer -y
```

https://github.com/oguzhaninan/Stacer


### Ungroup Utilities on Gnome Desktop (Does not appear to be a permanent solution)
```
gsettings set org.gnome.desktop.app-folders folder-children ['']
```

### Find Windows 10 Product Key - Only works where the license key is embedded into the hardware (mainly laptops)
```
sudo cat /sys/firmware/acpi/tables/MSDM | tail -c 32 | xargs -0 echo
```
### Completely remove a package

```
sudo apt-get purge --auto-remove packagename
```
https://askubuntu.com/questions/187888/what-is-the-correct-way-to-completely-remove-an-application

### Convert M4A audio files to MP3
Remeber to install FFmpeg first

```
ffmpeg -i audio.m4a -acodec libmp3lame -ab 256k audio.mp3
ffmpeg -i audio.m4a -acodec libmp3lame audio.mp3
ffmpeg -v 5 -y -i audio.m4a -acodec libmp3lame -ac 2 -ab 192k audio.mp3
```


### Nmap

Command Line Utility for network discovery and security auditing.
```
sudo apt-get install nmap
sudo nmap -sn 192.168.1.0/24
```
https://nmap.org/

### get-iplayer Snap
Command Line tool for downloading tv and radio programmes from the last 30 days from the BBC iPlayer.
```
sudo snap install get-iplayer
```
https://snapcraft.io/install/get-iplayer/ubuntu

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

    youtube-dl -U

### Useful Links

https://www.omgubuntu.co.uk/2017/05/how-to-update-gnome-extensions

https://extensions.gnome.org/extension/1160/dash-to-panel/

https://extensions.gnome.org/extension/750/openweather/

https://extensions.gnome.org/extension/836/internet-radio/

https://addons.mozilla.org/en-US/firefox/addon/gnome-shell-integration/

https://odio.io/

https://itsfoss.com/how-to-find-what-devices-are-connected-to-network-in-ubuntu/

https://github.com/ytdl-org/youtube-dl

https://linuxappstore.io/
