# npm

## 代理

```bash
npm config set proxy http://127.0.0.1:7788
npm config set https-proxy http://127.0.0.1:7788
```

-   取消代理

```bash
npm config delete proxy
npm config delete https-proxy
```

>   用socks5就报错- -
>
>   推荐使用yarn，npm是真的慢
>

## 镜像

```bash
npm config set registry https://registry.npmmirror.com
# 验证镜像
npm config get registry
```

>   如果返回[https://registry.npmmirror.com](https://registry.npmmirror.com/)，说明镜像配置成功

### 替换镜像

|      镜像名      |                    镜像地址                     |
| :--------------: | :---------------------------------------------: |
|      官方源      |           https://registry.npmjs.org/           |
|       淘宝       |         https://registry.npmmirror.com          |
|      腾讯云      |      http://mirrors.cloud.tencent.com/npm/      |
| 中国科学技术大学 |        https://npmreg.proxy.ustclug.org/        |
|      华为云      | https://mirrors.huaweicloud.com/repository/npm/ |

> [https://my.oschina.net/tangshi/blog/699190](https://my.oschina.net/tangshi/blog/699190)\
> [https://stackoverflow.com/questions/7559648/is-there-a-way-to-make-npm-install-the-command-to-work-behind-proxy](https://stackoverflow.com/questions/7559648/is-there-a-way-to-make-npm-install-the-command-to-work-behind-proxy)\
> [https://blog.csdn.net/yanzi1225627/article/details/80247758](https://blog.csdn.net/yanzi1225627/article/details/80247758)
>
> [腾讯云](http://mirrors.cloud.tencent.com/help/npm.html)

