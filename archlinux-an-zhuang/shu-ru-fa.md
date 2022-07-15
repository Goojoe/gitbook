# 输入法
```
sudo pacman -S fcitx5 \
fcitx5-chinese-addons \
fcitx5-gtk \
fcitx5-qt \
fcitx5-pinyin-zhwiki \
fcitx5-pinyin-sougou \
fcitx5-pinyin-moegirl-rime \
fcitx5-material-color
```
## 集成
```
sudo vim /etc/environment

GTK_IM_MODULE=fcitx
QT_IM_MODULE=fcitx
XMODIFIERS=@im=fcitx
INPUT_METHOD=fcitx
SDL_IM_MODULE=fcitx
GLFW_IM_MODULE=ibus

reboot

```




https://wiki.archlinux.org/title/Fcitx5_(%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87)