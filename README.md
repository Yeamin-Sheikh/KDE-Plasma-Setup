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
sudo pacman -S --needed base-devel git && git clone https://aur.archlinux.org/yay-git ~/Yay && cd ~/Yay && makepkg -si --noconfirm && cd && yay -S --noconfirm google-chrome && sudo pacman -S --noconfirm bluez blueman bluez-utils && sudo modprobe btusb && sudo systemctl enable bluetooth && sudo systemctl start bluetooth
```
### STEP 1: YAY
```sh
sudo pacman -S --needed base-devel git &&
git clone https://aur.archlinux.org/yay-git ~/Yay &&
cd ~/Yay &&
makepkg -si --noconfirm &&
cd &&
yay -S --noconfirm google-chrome &&
sudo pacman -S --noconfirm bluez blueman bluez-utils &&
sudo modprobe btusb &&
sudo systemctl enable bluetooth &&
sudo systemctl start bluetooth
```
