# Setup Manjaro

These are the instruction that I used to setup my Manjaro disto

## Software

- Tilix
- Fish
- Okular
- Visual Studio Code
- Rust
- Telegram
- Intellij Ultimate
- onedrive
- Gnome DE
- Google translate on terminal
- Docker
  ```fish
     sudo pacman -S docker docker-compose
     sudo usermod -aG docker $USER
     sudo systemctl start docker
     sudo systemctl enable docker
     alias dk "docker"
     funcsave dk
  ```
- SSH for Github
  ```fish
     ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
     ssh-add ~/.ssh/id_rsa
     sudo pacman -Sy xclip
     xclip -sel clip < ~/.ssh/id_rsa.pub
  ```
  and insert It at: https://github.com/settings/keys

## Codes

```shell
sudo pacman -Syu
sudo pacman -Sy tilix fish code telegram-desktop okular rust translate-shell
chsh -s /usr/bin/fish

mkdir .packages && cd .packages && git clone https://aur.archlinux.org/intellij-idea-ultimate-edition.git && cd intellij-idea-ultimate-edition && makepkg -si <<< Y && cd ..

git clone https://aur.archlinux.org/onedrive.git && cd onedrive && makepkg -si <<< Y && cd ..

sudo pacman -S gnome-extra gdm manjaro-gnome-assets manjaro-gdm-theme manjaro-settings-manager && sudo systemctl -f enable gdm.service

set -U fish_user_paths /home/luca/.cargo/bin/ $fish_user_paths
```

## Drivers

- stampante Epson SX525WD
  '''
  git clone https://aur.archlinux.org/epson-inkjet-printer-workforce-635-nx625-series.git && makepkg -si
  '''
  and then RESTART

- Bluethoot:
  ```
  wget https://github.com/winterheart/broadcom-bt-firmware/raw/master/brcm/BCM43142A0-04ca-2006.hcd
  sudo mv BCM43142A0-04ca-2006.hcd /lib/firmware/brcm/
  ```
  and then RESTART


## Other commands

- uname -r : view kernel
