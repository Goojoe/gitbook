# 使用Gitbash在Windows-Terminal_VSCode使用zsh

Windows默认的终端是cmd,我个人觉得不是很好用，所以今天教大家使用Gitbash在Windows Termianl  VSCode中使用zsh,让你的终端更好用

## 前言

### zsh简介

>   更加强大的Shell,bash,Tab自动补全，命令高亮
>
>   [Zsh](https://www.zsh.org/) 是一款功能强大的 [Shell](https://wiki.archlinux.org/title/Shell) 软件，既可以作为交互式终端来使用，也可以作为脚本语言解释器来使用。它在兼容 POSIX 的 sh 的同时（默认不兼容，仅在使用 `emulate sh` 时兼容），还改进了 [Tab 补全](https://zsh.sourceforge.io/Guide/zshguide06.html)和[通配符](https://zsh.sourceforge.io/Doc/Release/Expansion.html)等功能。

由于安装zsh需要访问Github,大家需要下面的东西

![image-20220721133025285](https://images.weserv.nl/?url=https://i0.hdslb.com/bfs/album/1a70cad4899e926b97ff50cd2ff897cd81a3e533.png)

## 正文

###　1.安装`Windows Termianl`

-   [微软商店  Microsoft Store](https://apps.microsoft.com/store/detail/windows-terminal/9N0DX20HK701)
    -   搜索`Windows Termianl`安装
-   [Github](https://github.com/microsoft/terminal/releases)

>   下载`.msixbundle`后缀的文件安装，如果没有下面的界面
>
>   ![image-20220721134328429](https://images.weserv.nl/?url=https://i0.hdslb.com/bfs/album/4e6af4af8e0e0e2cac949075cb84f777bc9fa166.png)
>
>   请尝试更新`应用安装程序`(Microsoft Store微软商店)

### 2.安装`Git For Windows`

-   [官网](https://git-scm.com/download/win)

![image-20220721134711895](https://images.weserv.nl/?url=https://i0.hdslb.com/bfs/album/01b687fb4d7faa8cb9d302666784e9d7c409284a.png)

-   安装界面

![image-20220721135127456](https://images.weserv.nl/?url=https://i0.hdslb.com/bfs/album/a026217f1423abbdbb59d90e855082272eedc59a.png)

其他的一路`Next`就可以了

### 3.下载zsh

-   [下载zsh](https://packages.msys2.org/package/zsh?repo=msys&variant=x86_64)

![image-20220721135421314](https://images.weserv.nl/?url=https://i0.hdslb.com/bfs/album/210c5a89b53fa0f1a8b6179c4fb1df880f060ff7.png)

下载并解压,可用[7-Zip-zstd](https://github.com/mcmilk/7-Zip-zstd/releases)解压

![image-20220721135742603](https://images.weserv.nl/?url=https://i0.hdslb.com/bfs/album/fc06a83fc46b37710998e5a3186b05d663d01dcc.png)

粘贴到Git安装目录，默认安装目录为`C:\Program Files\Git`

![image-20220721135917072](https://images.weserv.nl/?url=https://i0.hdslb.com/bfs/album/c529d26a4af79d70afc0b368bd0ab7cd9087ac18.png)

### 4.配置Windows Termianl

1.   将Gitbash改为`默认配置文件`

![image-20220721140154214](https://images.weserv.nl/?url=https://i0.hdslb.com/bfs/album/f8edd775aa1d2f0ce79dedb47f5184a6cb3f4c7b.png)

然后新开窗口输入`zsh`会出现下面窗口

![image-20220721145654328](https://images.weserv.nl/?url=https://i0.hdslb.com/bfs/album/edb94ed9b78aa35aa2be798cd2e6756275cc7331.png)

-   按下 `0` 将创建一个只包含注释的 `~/.zshrc` 文件，在下次启动时不会再次弹出设置选项。
-   按下 `1` 即可进入设置

```
Please pick one of the following options:

(1)  Configure settings for history, i.e. command lines remembered
     and saved by the shell.  (Recommended.)

(2)  Configure the new completion system.  (Recommended.)

(3)  Configure how keys behave when editing command lines.  (Recommended.)

(4)  Pick some of the more common shell options.  These are simple "on"
     or "off" switches controlling the shell's features.

(0)  Exit, creating a blank ~/.zshrc file.

(a)  Abort all settings and start from scratch.  Note this will overwrite
     any settings from zsh-newuser-install already in the startup file.
     It will not alter any of your other settings, however.

(q)  Quit and do nothing else.  The function will be run again next time.
--- Type one of the keys in parentheses ---
```

根据提示完成设置即可。也可以创建一个只包含注释的 `~/.zshrc` 文件以使用默认值(按`0`)

看不懂请使用翻译

-   [百度翻译](https://fanyi.baidu.com/)
-   [谷歌翻译](https://translate.google.cn/)
-   [Deepl](https://www.deepl.com/translator)

修改字体

默认的字体没有图标，需要安装Nerd Font支持图标,否则会乱码

>   **Nerd Fonts** 是一个使用大量字体图标来解决程序员在开发过程中缺少合适字体的问题的项目。它可以从流行的字体图标库中将大量外部字体引入待开发的项目中，它支持的字体图标库包括 [Font Awesome ](https://github.com/FortAwesome/Font-Awesome), [Devicons ](https://vorillaz.github.io/devicons/), [Octicons ](https://github.com/primer/octicons), and [others](https://github.com/ryanoasis/nerd-fonts/blob/master/readme_cn.md#glyph-sets).
>
>   -   [Github介绍](https://github.com/ryanoasis/nerd-fonts/blob/master/readme_cn.md)

前往

-   [NerdFont](https://www.nerdfonts.com/font-downloads)

>   注意:`Ctrl+F`是搜索不到名字的

-   [Github](https://github.com/ryanoasis/nerd-fonts/releases)

    下载字体

推荐字体
-   FiraMono
-   FiraCode
-   Noto(思源黑体)
-   Meslo(powerlevel10k主题推荐)
-   Hack

下载并安装字体

#### 设置字体

-   Windows Termianl设置

![image-20220721142032157](https://images.weserv.nl/?url=https://i0.hdslb.com/bfs/album/e207c21eac94f24a1d5c775273cb10dd1f4ad55e.png)

![image-20220721142104438](https://images.weserv.nl/?url=https://i0.hdslb.com/bfs/album/dce9a5adddaec1475175fa03dabf2c3c43a7f2ee.png)

-   Gitbash设置

`Windows+S`搜索Gitbash,或者右键`Git bash`(如果在安装页面配置了的话)

![image-20220721142556568](https://images.weserv.nl/?url=https://i0.hdslb.com/bfs/album/91c29a3620d1cb89d3c919f11d51b1bc215ed6da.png)



### 5.安装`oh my zsh`

```
// 使用curl，系统自带
$ sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"

// 使用Wget,windows没有
$ sh -c "$(wget https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"
```



### 6.配置主题

#### 安装[powerlevel10k](https://github.com/romkatv/powerlevel10k)

```
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
```

编辑`~/.zshrc`

改为
```
ZSH_THEME="powerlevel10k/powerlevel10k"
```

![image-20220721175638328](https://images.weserv.nl/?url=https://i0.hdslb.com/bfs/album/19615c7ce97694c95b5d41e61334b2faeefc433b.png)

刷新配置文件

```text
source ~/.zshrc
```

重启`Windows Termianl`



### 7.配置插件

-   `zsh-autosuggestions`插件

`zsh-autosuggestions`可以快速将历史命令呈现出来，具体可参考[官方说明](https://github.com/zsh-users/zsh-autosuggestions)

```text
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

编辑`~/.zshrc`

![image-20220721181209069](https://images.weserv.nl/?url=https://i0.hdslb.com/bfs/album/f5c74d77fcf3206bd863a1feedc10b8cce3a1fab.png)

```text
source ~/.zshrc
```

参考

>   https://zhuanlan.zhihu.com/p/455925403
>   https://segmentfault.com/a/1190000015155864
>
>   https://arch.icekylin.online/advanced/optional-cfg-1.html#%F0%9F%9A%80-zsh
>
>   https://zhuanlan.zhihu.com/p/61447507