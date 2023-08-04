# HyprV4
This is V4 of the Hyprland install script

It contains a collection of dot config files for hyprland with a simple install script.
IMPORTANT - This script is meant to run on a clean fresh Arch install on physical hardware

You can grab the config files and install packages by hand with the command listed below

Do this ONLY if you need Nvidia support (do this first)
```
yay -S linux-headers nvidia-dkms qt5-wayland qt5ct libva libva-nvidia-driver-git

Add modules: nvidia nvidia_modeset nvidia_uvm nvidia_drm to /etc/mkinitcpio.conf

Generate new image: sudo mkinitcpio --config /etc/mkinitcpio.conf --generate /boot/initramfs-custom.img

Add/create the following: options nvidia-drm modeset=1 in /etc/modprobe.d/nvidia.conf

reboot!
```

Now install the below for Hyprland

```
yay -S hyprland kitty jq mako waybar-hyprland swww swaylock-effects \
wofi wlogout xdg-desktop-portal-hyprland swappy grim slurp thunar \
polkit-gnome python-requests pamixer pavucontrol brightnessctl bluez \
bluez-utils blueman network-manager-applet gvfs thunar-archive-plugin \
file-roller btop pacman-contrib starship ttf-jetbrains-mono-nerd \
noto-fonts-emoji lxappearance xfce4-settings sddm-git sddm-sugar-candy-git 
```

Or you can use the attached script "set-hypr" to install everything for you.
-

<details>
  <summary><strong> After Done </strong></summary>

Any Nerd Fonts installed and used by your terminal emulator to display icon (Highly Recommended: JetBrains Mono, since most of the config using this font)

You can use lime-desu script to download any Nerd Fonts (requires [fzf](https://github.com/junegunn/fzf))
```
sudo pacman -S fzf wget
```
Script to download Fonts
```
bash -c "$(curl -Ls https://raw.githubusercontent.com/lime-desu/bin/main/nf-dl)"
```
  
install all font manual
```
pacman -S ttf-dejavu ttf-liberation ttf-droid ttf-ubuntu-font-family noto-fonts noto-fonts-cjk ttf-font-awesome

yay -S ttf-gelasio-ib ttf-caladea ttf-carlito ttf-liberation-sans-narrow ttf-ms-fonts
```

install obs-studio & font-manager
```
pacman -S obs-studio
yay -S font-manager
```
install webcord it just discord but can sharing srceen on wayland&hyprland
```
git clone https://aur.archlinux.org/webcord.git
cd webcord
makepkg -si
```
install AppImageLauncher for just use appimage
```
yay -S AppImageLauncher
```
install imagemagick for custom neofetch with image like .png|.jpg|.gif (requires [neofetch config](https://github.com/oniichanx/neofetch))
```
sudo pacman -S imagemagick
```

