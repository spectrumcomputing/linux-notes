## Ubuntu Post Clean Installation Extras

### Install required packages

```
sudo apt-get install gnome-tweak-tool arc-theme apt-transport-https ca-certificates curl software-properties-common gcc g++ make chrome-gnome-shell
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

### Docker (Ubuntu 18.04)

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

### Flatpak

```
sudo add-apt-repository ppa:alexlarsson/flatpak  
sudo apt update  
sudo apt install flatpak  
sudo apt install gnome-software-plugin-flatpak  
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.

```
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

### Find Windows 10 Product Ket
```
sudo cat /sys/firmware/acpi/tables/MSDM | tail -c 32 | xargs -0 echo
```

### Useful Links

https://www.omgubuntu.co.uk/2017/05/how-to-update-gnome-extensions

https://extensions.gnome.org/extension/1160/dash-to-panel/

https://addons.mozilla.org/en-US/firefox/addon/gnome-shell-integration/
