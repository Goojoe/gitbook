# pip

## 代理
### 配置文件

```conf
~/.pip/pip.conf
```

编辑文件

```conf
[global]
proxy=http://127.0.0.1:1087
```

> 注意不支持socks5

## 镜像

```bash
pip config set global.index-url https://mirrors.aliyun.com/pypi/simple

# 验证镜像
pip3 config list
```
> https://mirrors.tuna.tsinghua.edu.cn/help/pypi/

### 替换镜像

>   替换`https://mirrors.aliyun.com/pypi/simple`

|      镜像名      |                   镜像地址                    |
| :--------------: | :-------------------------------------------: |
|      官方源      |        https://pypi.python.org/simple         |
|      阿里云      |    https://mirrors.aliyun.com/pypi/simple     |
|     清华大学     |     https://mirror.baidu.com/pypi/simple      |
|      腾讯云      | https://mirrors.cloud.tencent.com/pypi/simple |
| 中国科学技术大学 |    https://pypi.mirrors.ustc.edu.cn/simple    |
|       豆瓣       |        http://pypi.douban.com/simple/         |

