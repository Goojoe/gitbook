# docker

## 代理

在执行`docker pull`时，是由守护进程`dockerd`来执行。因此，代理需要配在`dockerd`的环境中。而这个环境，则是受`systemd`所管控，因此实际是`systemd`的配置。

```bash
# 创建文件夹
sudo mkdir -p /etc/systemd/system/docker.service.d
# 创建配置文件
sudo touch /etc/systemd/system/docker.service.d/proxy.conf
# 使用vim编辑文件
sudo vim /etc/systemd/system/docker.service.d/proxy.conf
```
-   添加

```conf
[Service]
Environment="ALL_PROXY=socks5://127.0.0.1:7788"
```

## 镜像

``` bash
# 使用vim编辑配置文件,没有则创建
vim /etc/docker/daemon.json
```

-   添加

```json
{
"registry-mirrors": [
"https://registry.cn-hangzhou.aliyuncs.com",
"https://hub-mirror.c.163.com",
"https://mirror.baidubce.com"
]
}
```

## 重启生效

```bash
sudo systemctl daemon-reload
sudo systemctl restart docker
sudo systemctl status docker
```

>https://cloud.tencent.com/developer/article/1806455
