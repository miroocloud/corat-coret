# New fedora gnome
- sudo hostnamectl set-hostname "Penguin"
- gsettings set org.gnome.desktop.wm.preferences button-layout "appmenu:minimize,maximize,close"

# Configure DNF
- sudo nano /etc/dnf/dnf.conf
```sh
# see `man dnf.conf` for defaults and possible options

[main]
fastestmirror=True
max_parallel_downloads=10
```

# RPM Fusion
- sudo dnf install https://mirrors.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm

- sudo dnf install https://mirrors.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm

# Flathub
- flatpak remote-add --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo

# Fuse (AppImage)
- dnf install fuse fuse-libs

# GPU Driver
## Nvdia drive
- sudo dnf install nvidia-gpu-firmware
## AMD gpu
- sudo dnf install xorg-x11-drv-amdgpu vulkan-tools mesa-vulkan-drivers
