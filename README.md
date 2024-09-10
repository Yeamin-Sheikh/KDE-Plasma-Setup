# KDE-Plasma-Setup
## PART 1: PREINSTALL
### STEP 1: DISK PARTITIONING
```sh
lsblk
cfdisk /dev/nvme0n1
mkfs.fat -F32 /dev/nvme0n1p6
mkfs.ext4 /dev/nvme0n1p7
mount /dev/nvme0n1p7 /mnt
mkdir /mnt/boot &&
mount /dev/nvme0n1p6 /mnt/boot
```
### STEP 2: INTERNET CONNECTION
```sh
iwctl
station wlan0 connect wifiname
password
exit
ping -c3 1.1.1.1
```
### STEP 3: ARCHINSTALL
```sh
pacman -Syy &&
pacman-key --init &&
pacman-key --populate archlinux &&
pacman -S --noconfirm archlinux-keyring archinstall &&
archinstall
```
## PART 2: POSTINSTALL
### ONE CODE
```sh
sudo pacman -S --needed base-devel git && git clone https://aur.archlinux.org/yay-git ~/Yay && cd ~/Yay && makepkg -si --noconfirm && cd ~/ && sudo pacman -S --noconfirm bluez blueman bluez-utils && sudo modprobe btusb && sudo systemctl enable bluetooth && sudo systemctl start bluetooth && 
```
### STEP 1: AUR (YAY)
```sh
sudo pacman -S --needed base-devel git &&
git clone https://aur.archlinux.org/yay-git ~/Yay &&
cd ~/Yay &&
makepkg -si --noconfirm &&
cd ~/
```
### STEP 2: BLUETOOTH SUPPORT
```sh
sudo pacman -S --noconfirm bluez blueman bluez-utils &&
sudo modprobe btusb &&
sudo systemctl enable bluetooth &&
sudo systemctl start bluetooth
```
### STEP 3: ADDITIONAL PROGRAMS
```sh
sudo pacman -S --noconfirm ldns &&
sudo pacman -S --noconfirm npm &&
sudo pacman -S --noconfirm flatpak &&
sudo pacman -S --noconfirm timeshift && 
sudo pacman -S --noconfirm telegram-desktop && 
sudo pacman -S --noconfirm discord && 
sudo pacman -S --noconfirm fastfetch && 
sudo pacman -S --noconfirm nano && 
sudo pacman -S --noconfirm vim && 
sudo pacman -S --noconfirm flameshot  && 
sudo pacman -S --noconfirm viewnior  && 
sudo pacman -S --noconfirm libreoffice-fresh &&
yay -S --noconfirm caprine &&
yay -S --noconfirm ticktick  &&
yay -S --noconfirm spotify &&
yay -S --noconfirm visual-studio-code-bin &&
```
### MANUAL CONFIG:
```sh
sudo nano /etc/pacman.conf
# Uncomment Parallel Downloads
# Add ILoveCandy


```

### EXTRA COMMANDS:
```sh
ip addr
# IP Checker
```
```sh
export http_proxy=socks5h://USERNAME:PASSWORD@IP:PORT
# Socks5 Proxy
```
```sh
mkswap /dev/nvme0n1p8
swapon /dev/nvme0n1p8
# Make Swap
```
```sh
yay -S mkinitcpio-numlock
sudo nano /etc/mkinitcpio.conf
# write "numlock" before keymap
# Numlock on Startup
```
