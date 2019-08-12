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
```
sudo add-apt-repository ppa:xuzhen666/gnome-mpv
sudo apt-get update
sudo apt-get install gnome-mpv
```
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
### Convert M4A audio files to MP3

```
ffmpeg -i audio.m4a -acodec libmp3lame -ab 256k audio.mp3
ffmpeg -i audio.m4a -acodec libmp3lame audio.mp3
ffmpeg -v 5 -y -i audio.m4a -acodec libmp3lame -ac 2 -ab 192k audio.mp3
```

### Useful Links

https://www.omgubuntu.co.uk/2017/05/how-to-update-gnome-extensions

https://extensions.gnome.org/extension/1160/dash-to-panel/

https://extensions.gnome.org/extension/750/openweather/

https://extensions.gnome.org/extension/836/internet-radio/

https://addons.mozilla.org/en-US/firefox/addon/gnome-shell-integration/

https://kb.vmware.com/s/article/1002411

https://celluloid-player.github.io/installation.html

https://askubuntu.com/questions/537787/enable-3d-hw-acceleration-on-vmware-workstation-10-on-ubuntu-14-04

https://askubuntu.com/questions/187888/what-is-the-correct-way-to-completely-remove-an-application

https://odio.io/
