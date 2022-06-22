# yarn

## 安装

```bash
npm -g install yarn
yarn -v
```

## 代理

```bash
yarn config set proxy http://127.0.0.1:7788
yarn config set https-proxy http://127.0.0.1:7788
```

## 镜像

```bash
yarn config set registry https://registry.npmmirror.com
# 验证
yarn config get registry
```

### 替换镜像

|      镜像名      |                    镜像地址                     |
| :--------------: | :---------------------------------------------: |
|      官方源      |           https://registry.npmjs.org/           |
|       淘宝       |         https://registry.npmmirror.com          |
|      腾讯云      |      http://mirrors.cloud.tencent.com/npm/      |
| 中国科学技术大学 |        https://npmreg.proxy.ustclug.org/        |
|      华为云      | https://mirrors.huaweicloud.com/repository/npm/ |
