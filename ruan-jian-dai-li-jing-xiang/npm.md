# npm

代理

```bash
npm config set proxy http://127.0.0.1:1087
npm config set https-proxy http://127.0.0.1:1087
```

BASH

取消代理

```bash
npm config delete proxy
npm config delete https-proxy
```

BASH

用socks5就报错- -

推荐使用yarn，npm是真的慢

1. 镜像

```bash
npm config set registry https://registry.npmmirror.com
```

BASH

1. 验证命令

```bash
npm config get registry
```

BASH

如果返回[https://registry.npmmirror.com](https://registry.npmmirror.com/)，说明镜像配置成功。

> [https://my.oschina.net/tangshi/blog/699190](https://my.oschina.net/tangshi/blog/699190)\
> [https://stackoverflow.com/questions/7559648/is-there-a-way-to-make-npm-install-the-command-to-work-behind-proxy](https://stackoverflow.com/questions/7559648/is-there-a-way-to-make-npm-install-the-command-to-work-behind-proxy)\
> [https://blog.csdn.net/yanzi1225627/article/details/80247758](https://blog.csdn.net/yanzi1225627/article/details/80247758)
