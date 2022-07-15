# Aur Paru安装

```
sudo pacman -Syy

sudo pacman -S yay

yay -S paru
```


```
git clone https://aur.archlinux.org/paru.git

# makepkg设置
sudo vim /etc/makepkg.conf

MAKEPKG=j$(nproc)

cd paru/ && makepkg -si
```