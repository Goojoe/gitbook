# Git

## 代理

### SSH代理

 `~/.ssh/config` 后添加下面两行

```bash
ProxyCommand connect -S 127.0.0.1:10801 -a none %h %p

Host github.com
  User git
  Port 22
  Hostname github.com
  # 注意修改路径为你的路径
  IdentityFile "C:\Users\One\.ssh\id_rsa"
  TCPKeepAlive yes

Host ssh.github.com
  User git
  Port 443
  Hostname ssh.github.com
  # 注意修改路径为你的路径
  IdentityFile "C:\Users\One\.ssh\id_rsa"
  TCPKeepAlive yes
```
> https://gist.github.com/chenshengzhi/07e5177b1d97587d5ca0acc0487ad677?permalink_comment_id=3723065#gistcomment-3723065

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
