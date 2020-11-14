
    sudo apt install tvheadend
admin / admin
Crystal Palace

get-iplayer

https://software.opensuse.org/download.html?project=home%3Am-grant-prg&package=get-iplayer

    echo 'deb http://download.opensuse.org/repositories/home:/m-grant-prg/Raspbian_10/ /' | sudo tee /etc/apt/sources.list.d/home:m-grant-prg.list
    curl -fsSL https://download.opensuse.org/repositories/home:m-grant-prg/Raspbian_10/Release.key | gpg --dearmor | sudo tee /etc/apt/trusted.gpg.d/home_m-grant-prg.gpg > /dev/null
    sudo apt update
    sudo apt install get-iplayer

https://github.com/get-iplayer/get_iplayer/wiki/filenames

    makedir /home/pi/recordings-radio
    makedir /home/pi/recordings-tv

    get_iplayer --prefs-add --outputradio="/home/pi/recordings-radio/"
    get_iplayer --prefs-add --outputtv="/home/pi/recordings-tv/"

Samba Server

https://pimylifeup.com/raspberry-pi-samba/

    sudo apt-get install samba samba-common-bin

    sudo nano /etc/samba/smb.conf

    [RaspberryPi]
    path = /home/pi/
    writeable=Yes
    create mask=0777
    directory mask=0777
    public=no

    sudo smbpasswd -a pi (Choose Password)

    sudo systemctl restart smbd

    hostname -I
    
    [Raspberry Pi Share]
    Comment = Pi shared folder
    Path = "/home/pi/share"
    Browseable = yes
    Writeable = Yes
    only guest = no
    create mask = 0777
    directory mask = 0777
    Public = yes
    Guest ok = yes



