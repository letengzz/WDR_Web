# yarn 包管理工具

yarn 是由 Facebook 在 2016 年推出的新的 Javascript 包管理工具

![image-20231026180709980](https://cdn.jsdelivr.net/gh/letengzz/tc2/img202310261807750.png)

- 官方网址： https://yarnpkg.com/

**特点**：

- 速度超快：yarn 缓存了每个下载过的包，所以再次使用时无需重复下载。 同时利用并行下载以最大化资源利用率，因此安装速度更快
- 超级安全：在执行代码之前，yarn 会通过算法校验每个安装包的完整性
- 超级可靠：使用详细、简洁的锁文件格式和明确的安装算法，yarn 能够保证在不同系统上无差异的工作

## 安装yarn

使用 npm 安装 yarn：

```shell
npm i -g yarn
```

## 常用命令

![image-20231026201034999](https://cdn.jsdelivr.net/gh/letengzz/tc2/img202310262010927.png)

yarn 全局安装包的位置可以通过 `yarn global bin` 来查看

```shell
yarn global bin
```

**注意**：全局安装的包不可用 ，需要目录放入path中

## 配置淘宝镜像

配置淘宝镜像命令：

```shell
yarn config set registry https://registry.npmmirror.com/
```

可以通过 `yarn config list` 查看 yarn 的配置项：

```shell
yarn config list
```

