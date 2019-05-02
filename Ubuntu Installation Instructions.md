## Ubuntu Post Clean Installation Extras

### Install required packages

```
sudo apt-get install neofetch gnome-tweak-tool arc-theme apt-transport-https ca-certificates curl software-properties-common gcc g++ make pavucontrol chrome-gnome-shell
```
### Replace Snap installed packages so icon themes work (Ubuntu 19.04)
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

### Docker (Ubuntu 19.04)

```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -  
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu disco nightly"  
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
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```
### Ungroup Utilities on Gnome Desktop
```
gsettings set org.gnome.desktop.app-folders folder-children ['']
```

### Vulkan Drivers for AMD Graphics Cards

```
sudo add-apt-repository ppa:oibaf/graphics-drivers
sudo apt update
sudo apt upgrade
sudo apt install libvulkan1 mesa-vulkan-drivers vulkan-utils
vulkaninfo | less
```
### Checking the version of Mesa Drivers
```
sudo apt install mesa-utils
glxinfo | grep "OpenGL version"
```


### Useful Links

https://www.omgubuntu.co.uk/2017/05/how-to-update-gnome-extensions

https://extensions.gnome.org/extension/1160/dash-to-panel/

https://medium.com/@Grigorkh/how-to-install-docker-on-ubuntu-19-04-7ccfeda5935

https://addons.mozilla.org/en-US/firefox/addon/gnome-shell-integration/
