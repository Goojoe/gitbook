# Ubuntu/Debian

1.2 卸载旧版本

```bash
 sudo apt-get remove docker docker-engine docker.io containerd runc
```

#### 1.3 使用 Docker 仓库进行安

```bash
sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common
```

#### 1.4 添加 Docker 的官方 GPG 密钥：

```bash
curl -fsSL https://mirrors.ustc.edu.cn/docker-ce/linux/ubuntu/gpg | sudo apt-key add -
```

#### 1.5 0EBF CD88 通过搜索指纹的后8个字符，验证密钥。

```bash
sudo apt-key fingerprint 0EBFCD88
# 输出
pub   rsa4096 2017-02-22 [SCEA]
      9DC8 5822 9FC7 DD38 854A  E2D8 8D81 803C 0EBF CD88
uid           [ unknown] Docker Release (CE deb) <docker@docker.com>
sub   rsa4096 2017-02-22 [S]
```

#### 1.6 设置稳定版仓库

```bash
sudo add-apt-repository \
   "deb [arch=amd64] https://mirrors.ustc.edu.cn/docker-ce/linux/ubuntu/ \
  $(lsb_release -cs) \
  stable"
```

#### 1.7 安装 Docker CE

```
sudo apt install docker-ce docker-ce-cli containerd.io -y
```

#### 1.8 验证安装

```
sudo docker run hello-world
```
