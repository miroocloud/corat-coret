# Fedora Workstation Fresh Setup

```sh
# Set hostname & GNOME button layout
sudo hostnamectl set-hostname "Penguin"
gsettings set org.gnome.desktop.wm.preferences button-layout "appmenu:minimize,maximize,close"

# Configure DNF
sudo nano /etc/dnf/dnf.conf

[main]
fastestmirror=True
max_parallel_downloads=10

# RPM Fusion (Free & Non-Free)
sudo dnf install https://mirrors.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm
sudo dnf install https://mirrors.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm

# Refressh dnf
sudo dnf upgrade --refresh

# Flathub
flatpak remote-add --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo

# AppImage support (Fuse)
sudo dnf install fuse fuse-libs

# GPU Drivers
# NVIDIA
sudo dnf install nvidia-gpu-firmware

# AMD
sudo dnf install xorg-x11-drv-amdgpu vulkan-tools mesa-vulkan-drivers
```

