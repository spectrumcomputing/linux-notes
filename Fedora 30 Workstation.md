## Fedora 30
### Always make sure you understand the commands given. Most of the sections include a link to the appropriate documentation

### Updating the system
```
sudo dnf check-update
sudo dnf update
```

### Arc Theme
```
sudo dnf install gnome-tweak-tool arc-theme
```
### Papirus Icon Theme
```
wget -qO- https://raw.githubusercontent.com/PapirusDevelopmentTeam/papirus-icon-theme/master/install.sh | sh
```

### Removing LibreOffice
```
sudo dnf groupremove "LibreOffice"
sudo dnf erase libreoffice*
```

### Visual Studio Code
```
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo sh -c 'echo -e "[code]\nname=Visual Studio Code\nbaseurl=https://packages.microsoft.com/yumrepos/vscode\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/vscode.repo'
sudo dnf check-update
sudo dnf install code
```
https://code.visualstudio.com/docs/setup/linux#_rhel-fedora-and-centos-based-distributions

### NodeJS
```
sudo dnf install -y gcc-c++ make
curl -sL https://rpm.nodesource.com/setup_12.x | sudo -E bash -
sudo dnf install nodejs
node --version
npm --version
```

https://tecadmin.net/install-latest-nodejs-on-fedora/

### Cockpit
```
sudo dnf install cockpit cockpit-machines
sudo systemctl enable --now cockpit.socket
sudo firewall-cmd --add-service=cockpit
sudo firewall-cmd --add-service=cockpit --permanent
```

https://ip-address-of-machine:9090

Note: Copy ISO files to /var/libvirt/images

https://cockpit-project.org/running#fedora

### Enabling the RPM Fusion repositories

```
sudo dnf install https://download1.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm

sudo dnf install https://download1.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm
```
https://docs.fedoraproject.org/en-US/quick-docs/setup_rpmfusion/

### Enabling Multimedia support
```
sudo dnf install gstreamer1-libav gstreamer1-plugins-bad-free gstreamer1-plugins-bad-free gstreamer1-plugins-bad-free-extras gstreamer1-plugins-bad-freeworld gstreamer1-plugins-bad-nonfree gstreamer1-plugins-good gstreamer1-plugins-ugly lame-libs lame-libs
```

https://docs.fedoraproject.org/en-US/quick-docs/assembly_installing-plugins-for-playing-movies-and-music/
