# ArchLinux安装

## 1.下载安装镜像iso

-   官方:https://archlinux.org/download/
-   阿里云镜像:http://mirrors.aliyun.com/archlinux/iso/latest/

![image-20220710220618138](https://images.weserv.nl/?url=https://i0.hdslb.com/bfs/album/f05a1a4f86adc267d8d8ad4b306484c2e6194095.png)

## 2.验证安装镜像

下载完镜像后，找到系统镜像，在文件路径下输入cmd并按Enter(回车)

![image-20220710220936126](https://images.weserv.nl/?url=https://i0.hdslb.com/bfs/album/70d156bc5311b969d69439fda7ed14780142a315.png)

输入

```
CertUtil -hashfile <!系统镜像文件名!> MD5
```

![image-20220710221222655](https://images.weserv.nl/?url=https://i0.hdslb.com/bfs/album/29295585bdabfb800e1408d1f64719d52584dc01.png)

## 3.Vmware安装

不做说明

## 4.连接WIFI

```
# 设置字体
setfont ter-132n
# 进入iwd，连接wifi
iwctl
# 列出网卡名字
devices list
# 搜索Wifi网络
station wlan0 scan
# 显示网络
station wlan0 get-networks
# 连接网络
station wlan0 connect ChinaNet-6uG9Cu
# 退出
exit
# 测试网络
ping -c 4 114.114.114.114
```

## 5.设置pacman镜像

```
# 查看镜像列表
cat /etc/pacman.d/mirrorlist
# 寻找镜像
reflector -c China --age 24 --sort rate --protocol https --save /etc/pacman.d/mirrorlist
# 查看镜像列表
cat /etc/pacman.d/mirrorlist
# 同步软件源
pacman -Syy
```

## 6.磁盘分区

```
# 查看磁盘
lsblk
# gdisk分区
gdisk /dev/<磁盘名>

# 建立efi分区
n
# 两次enter
# efi分区
+512M
# efi分区类型
ef00

# 建立linux主分区
n
# 两次enter
# Linux分区
+95G
# 默认分区类型是linux系统 enter

# 建立SWAP虚拟缓存
n
# 两次enter
# SWAP分区
+4G
# SWAP分区
8200
```

## 7.格式化分区

```
# 格式化efi
mkfs.vfat /dev/nvme0n1px
# 格式化linux分区
mkfs.xfs /dev/nvme0n1px
# Swap分区
mkswap /dev/nvme0n1px
#　查看分区
lsblk -f
```

## 8.挂载磁盘

```
# 挂载linux系统分区
mount /dev/nvme0n1px /mnt
# 新建efi文件
mkdir -p /mnt/boot/efi
# 挂载efi分区
mount /dev/nvme0n1px /mnt/boot/efi
# swap分区
swapon /dev/nvme0n1px
# 查看分区
lsblk
```

## 9.安装系统

```
# 安装基础包
pacstrap /mnt linux linux-firmware linux-headers base base-devel vim git bash-completion dhcpcd iwd ntf-3g sudo reflector mtools dosfstools os-prober wpa_supplicant
# 生成文件系统
genfstab -U /mnt >> /mnt/etc/fstab
# 验证
cat /mnt/etc/fstab
# 进入系统
arch-chroot /mnt
# 刷新镜像
pacman -Syy
# 安装软件
pacman -S grub efibootmgr efivar networkmanager intel-ucode 
# grub 安装
grub-install /dev/nvme0n1
# 修改grub设置
vim /etc/default/grub
```

![image-20220713115944363](https://images.weserv.nl/?url=https://i0.hdslb.com/bfs/album/43185a14b4a8cf93b894d5949fffec2a7fb3c814.png)

```
# 生成grub配置文件
grub-mkconfig -o /boot/grub/grub.cfg
# 将networkmanager自启动
systemctl enable NetworkManager
# 增加root用户密码
passwd
#　退出系统
exit
```

## 10.取消挂载系统

```
# 查看系统信息
lsblk
# 卸载系统
umount -R /mnt
# 重启
reboot
```

## 11.基本配置

```
# 调整字体
setfont ter-132n
# 连接wifi
# 查看网卡名称
ip a
# 进入网络管理器ui
nmtui
# 选择Activate a connection
# OK > Back > Exit

# 测试网络
ping -c 4 223.6.6.6

# 改主机名
vim /etc/hostname
# 输入archlinux

# 改主机名
vim /etc/hosts
127.0.0.1	loaclhost
::1			loaclhost 
127.0.1.1	archlinux.loacldomain	archlinux

# 设置时间
timedatectl set-timezone Asia/Shanghai
# 启用ntp
timedatectl set-ntp true
# 查看状态
timedatectl status

# 环境变量
不写了

# 增加用户
useradd --create-home goojoe
id goojoe
# 设置密码
passwd goojoe
# 增加用户组
usermod -aG wheel,users,storage,power,lp,adm,optical goojoe

# 设置vim环境变量
export EDITOR=vim
# 设置普通用户使用超级用户命令
visudo
# 去注释# %whell ALL=(ALL) ALL
# 重启
reboot
```

## 12.安装图形界面

```
# 调整字体
setfont ter-132n

# 同步镜像
pacman -Syy
# 安装xorg
pacman -S xorg plasma-meta konsole dolphin ark appstream-qt appstream gwenview steam firefox firefox-i18n-zh-cn kate spectacle wget netease-cloud-music vlc network-manager-applet

# 安装kde
pacman -S plasma kde-applications packagekit-qt5 sddm

# 自启动
systemctl enable sddm

# 安装字体
pacman -S noto-fonts noto-fonts-cjk noto-fonts-extra noto-fonts-emoji ttf-dejavu ttf-liberation wqy-zenhei wqy-microhei

# 配置语言
vim /etc/locale.gen
#en_US.UTF-8
#zh_CN.UFT-8

vim /etc/locale.conf
LANG=en_US.UFT-8
# LANG=zh_CN.UFT-8

# 生成字体
locale-gen

# 更改字体渲染器
vim /etc/profile.d/freetype2.sh
# 去注释#export xxx
```

## 13.安装显卡驱动

```
# intel核显
pacman -S mesa lib32-mesa vulkan-intel lib32-vulkan-intel
# 英伟达独显
pacman -S nvidia nvidia-settings lib32-nvidia-utils
# 双显卡切换工具
yay -S optimus-manager optimus-manager-qt
sudo systemctl enable optimus-manager
```

## 14.其他驱动

```
pacman -S alsa-utils pulseaudio pulseaudio-bluetooth

# pacman -Scc
# y y
reboot
```

