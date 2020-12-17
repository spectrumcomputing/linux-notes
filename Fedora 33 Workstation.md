## Fedora 33
### Always make sure you understand the commands given. Most of the sections include a link to the appropriate documentation

### Updating the system
```
sudo dnf check-update
sudo dnf update
```

### Gnome Tweak Tool
```
sudo dnf install gnome-tweak-tool
```
### Arc Theme`
```
sudo dnf copr enable mhdahmad/workstation
sudo dnf install arc-theme
```

### Papirus Icon Theme
```
wget -qO- https://raw.githubusercontent.com/PapirusDevelopmentTeam/papirus-icon-theme/master/install.sh | sh
```
### Change Hostname
```
sudo hostnamectl set-hostname new-name
```

### Removing LibreOffice
```
sudo dnf groupremove "LibreOffice"
sudo dnf erase libreoffice*
```

### Cockpit
```
sudo dnf install cockpit cockpit-machines
sudo systemctl enable --now cockpit.socket
sudo firewall-cmd --add-service=cockpit
sudo firewall-cmd --add-service=cockpit --permanent
```

https://ip-address-of-machine:9090

Note: Copy ISO files to /var/lib/libvirt/images

https://cockpit-project.org/running#fedora

### Enabling the RPM Fusion repositories

```
sudo dnf install https://download1.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm

sudo dnf install https://download1.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm
```
https://docs.fedoraproject.org/en-US/quick-docs/setup_rpmfusion/

### Enabling Multimedia support
```
sudo dnf install gstreamer1-plugins-{bad-\*,good-\*,base} gstreamer1-plugin-openh264 gstreamer1-libav --exclude=gstreamer1-plugins-bad-free-devel

sudo dnf install lame\* --exclude=lame-devel

sudo dnf group upgrade --with-optional Multimedia
```

https://docs.fedoraproject.org/en-US/quick-docs/assembly_installing-plugins-for-playing-movies-and-music/


### Other Packages
```
sudo dnf install filezilla celluloid
```

### Fuse Spectrum Emulator
```
sudo dnf install fuse-emulator spectrum-roms fuse-emulator-roms
```
