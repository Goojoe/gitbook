# Git

## 代理

### SSH代理

 `~/.ssh/config` 后添加下面两行

```bash
Host github.com
    User git
    ProxyCommand nc -v -x 127.0.0.1:7788 %h %p
```

### Git代理

配置文件地址`~/.gitconfig`

-   命令行输入

```bash
# http代理
git config --global http.https://github.com.proxy socks5://127.0.0.1:7788
# https代理
git config --global https.https://github.com.proxy socks5://127.0.0.1:7788
```

## 镜像

### GitClone

```bash
git config --global url."https://gitclone.com/".insteadOf https://
```

>   下载会走镜像,上传请用代理
