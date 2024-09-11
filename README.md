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
sudo pacman -S --noconfirm obs-studio &&
sudo pacman -S --noconfirm proxychains-ng
sudo pacman -S --noconfirm ldns &&
sudo pacman -S --noconfirm npm &&
sudo pacman -S --noconfirm gimp &&
sudo pacman -S --noconfirm flatpak &&
sudo pacman -S --noconfirm ufw &&
sudo pacman -S --noconfirm timeshift && 
sudo pacman -S --noconfirm telegram-desktop && 
sudo pacman -S --noconfirm discord && 
sudo pacman -S --noconfirm fastfetch && 
sudo pacman -S --noconfirm nano && 
sudo pacman -S --noconfirm vim && 
sudo pacman -S --noconfirm flameshot  && 
sudo pacman -S --noconfirm viewnior  && 
sudo pacman -S --noconfirm libreoffice-fresh &&
sudo pacman -S --noconfirm p7zip && 
sudo pacman -S --noconfirm unrar && 
sudo pacman -S --noconfirm tar && 
sudo pacman -S --noconfirm rsync && 
sudo pacman -S --noconfirm exfat-utils && 
sudo pacman -S --noconfirm fuse-exfat && 
sudo pacman -S --noconfirm ntfs-3g && 
sudo pacman -S --noconfirm flac && 
sudo pacman -S --noconfirm jasper && 
sudo pacman -S --noconfirm aria2 &&
sudo pacman -S --noconfirm jdk-openjdk &&
yay -S --noconfirm caprine &&
yay -S --noconfirm ticktick  &&
yay -S --noconfirm spotify &&
yay -S --noconfirm visual-studio-code-bin &&
yay -S --noconfirm preload
yay -S --noconfirm auto-cpufreq
```
### STEP: JERRY
```sh
sudo pacman -S --noconfirm grep &&
sudo pacman -S --noconfirm sed &&
sudo pacman -S  --noconfirm curl &&
sudo pacman -S  --noconfirm fzf &&
sudo pacman -S  --noconfirm mpv &&
sudo pacman -S  --noconfirm rofi &&
sudo pacman -S  --noconfirm jq &&
yay -S --noconfirm ueberzugpp &&
sudo curl -sL github.com/justchokingaround/jerry/raw/main/jerry.sh -o /usr/local/bin/jerry &&
sudo chmod +x /usr/local/bin/jerry &&
jerry -e &&
jerry -c
```
### MANUAL CONFIG:
```sh
sudo nano /etc/pacman.conf
# Uncomment Parallel Downloads
# Add ILoveCandy
```
```sh
nano .bashrc
# alias jer='jerry -c'
# alias update='fastfetch && sudo pacman -Syu && yay'
```
```sh
sudo nano /etc/proxychains.conf
# 1) Navigate to the bottom of the file.
# 2) Comment the line that says "socks4  127.0.0.1 9050" by adding the # symbol.
# 3) Below that line, add your SOCKS5 proxy IP information in the following format:
#   socks5 IP PORT USERNAME PASSWORD
#
# USAGE:
# proxychains application_name
# nohup proxychains application_name
```
```sh
sudo ufw status &&
sudo systemctl enable ufw &&
sudo systemctl start ufw &&
sudo systemctl status ufw &&
#Firewall
```
```sh
sudo systemctl enable preload &&
sudo systemctl start preload &&
sudo systemctl status preload
# Preload
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
```sh
yay -S --noconfirm davinci-resolve 
# rocm-opencl-runtime: For AMD GPUs
# Davinci Resolve
```
```sh
sudo pacman -S --noconfirm reflector &&
sudo cp /etc/pacman.d/mirrorlist /etc/pacman.d/mirrorlist.bak &&
sudo reflector --verbose --latest 10 --protocol https --sort rate --save /etc/pacman.d/mirrorlist
# Mirrorlist
```
```sh
sudo grub-mkconfig -o /boot/grub/grub.cfg
# https://youtu.be/odgD_RdJjCU?si=oMMWW0X2OTmyxIDH&t=327
# Update the Grub
```
### NOTES
```sh
Get Brave, Free Download Manager & Calculator from Flatpak
Setup auto-cpufreq
```
