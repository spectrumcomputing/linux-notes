## Shortwave
#### Find and listen to internet radio stations

### Start by installing Rust
```
sudo apt-get install curl
curl https://sh.rustup.rs -sSf | sh
```
### Install other dependancies
```
sudo apt-get install libhandy-0.0-dev libhandy-0.0-0 libssl-dev appstream-util meson
```
### Build the package
```
git clone https://gitlab.gnome.org/World/Shortwave.git
cd Shortwave
meson --prefix=/usr build
ninja -C build
sudo ninja -C build install
```

https://gitlab.gnome.org/World/Shortwave
