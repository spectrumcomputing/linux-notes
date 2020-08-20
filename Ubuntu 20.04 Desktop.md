## Ubuntu 20.04 Additional Packages Installation Notes

You are advised not to copy and paste commands without knowing what they do.  There are links to more information throughout this document to additional information


### Install required packages

```
sudo apt-get install gnome-tweak-tool apt-transport-https ca-certificates curl software-properties-common chrome-gnome-shell build-essential

```
### Ubuntu Restricted Extras
```
sudo apt-get install ubuntu-restricted-extras 
```

### Additional GNOME Applications
```
sudo apt-get install gnome-photos gnome-weather gnome-music gnome-maps rhythmbox
```

### Papirus Icon Theme

```
sudo add-apt-repository ppa:papirus/papirus  
sudo apt update && sudo apt install papirus-icon-theme  
```

### Celluloid (formerly GNOME MPV)

```
sudo add-apt-repository ppa:xuzhen666/gnome-mpv
sudo apt-get update
sudo apt-get install celluloid
```
https://celluloid-player.github.io/installation.html


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
### Enable DVD Playback

```
sudo apt install libdvd-pkg && sudo dpkg-reconfigure libdvd-pkg
```
https://help.ubuntu.com/community/RestrictedFormats/PlayingDVDs

### Nmap

Command Line Utility for network discovery and security auditing.
```
sudo apt-get install nmap
sudo nmap -sn 192.168.1.0/24
```
https://nmap.org/


### youtube-dl 
Later versions of Ubuntu only ship with Python3 which is called python3 rather than python. This can cause some problems. This method of installation has been tested on Ubuntu 19.10

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

https://itsfoss.com/how-to-find-what-devices-are-connected-to-network-in-ubuntu/

https://github.com/PapirusDevelopmentTeam/papirus-icon-theme

https://github.com/jnsh/arc-theme

https://packages.debian.org/bullseye/arc-theme




