# KDE-Plasma-Setup
## PART1: PREINSTALL
### STEP1: DISK PARTITIONING
```sh
lsblk
cfdisk /dev/sda
mkfs.fat -F32 /dev/nvme0n1p6
mkfs.ext4 /dev/nvme0n1p7
mount /dev/nvme0n1p7 /mnt
mkdir /mnt/boot && mount /dev/nvme0n1p6 /mnt/boot
```
### STEP2: INTERNET
```sh
iwctl
station wlan0 connect NotAVirus.exe_5G
exit
ping -c3 1.1.1.1
```
### STEP3: ARCHINSTALL
```sh
pacman -Syy && pacman-key --init && pacman-key --populate archlinux && pacman -S --noconfirm archlinux-keyring archinstall && archinstall
```

Personally Customized KDE Plasma Setup <br>
```sh
sudo pacman -S --needed base-devel git &&
git clone https://aur.archlinux.org/yay-git ~/Yay &&
cd ~/Yay/yay-git &&
makepkg -si &&
cd &&
yay -S --noconfirm google-chrome
```
```sh
sudo pacman -S --needed base-devel git &&
git clone https://aur.archlinux.org/yay-git ~/Yay &&
cd ~/Yay/yay-git &&
makepkg -si &&
cd &&
yay -S --noconfirm google-chrome
```
```sh
sudo pacman -S --needed base-devel git &&
git clone https://aur.archlinux.org/yay-git ~/Yay &&
cd ~/Yay/yay-git &&
makepkg -si &&
cd &&
yay -S --noconfirm google-chrome
```
