# Windows 安装Node.js

打开 [Node.js官网](http://nodejs.org) 下载Node.js

- Node.js 官网：http://nodejs.org
- Node.js 中文站下载：http://nodejs.cn/download
- Node.js 历史版本：https://registry.npmmirror.com/binary.html?path=node

**注意**：

- LTS：长期支持版本
- Current：最新版

![image-20231003174023008](https://cdn.jsdelivr.net/gh/letengzz/tc2@main/img/Java/202310031740169.png)

也可以通过 https://nodejs.org/en/download 下载

![image-20231003174224837](https://cdn.jsdelivr.net/gh/letengzz/tc2@main/img/Java/202310031742716.png)

下载完毕后，双击安装Node.js

![image-20231003174749883](https://cdn.jsdelivr.net/gh/letengzz/tc2@main/img/Java/202310031747421.png)

![image-20231003174802617](https://cdn.jsdelivr.net/gh/letengzz/tc2@main/img/Java/202310031750726.png)

![image-20231003174846696](https://cdn.jsdelivr.net/gh/letengzz/tc2@main/img/Java/202310031750751.png)

![image-20231003174923260](https://cdn.jsdelivr.net/gh/letengzz/tc2@main/img/Java/202310031750138.png)

![image-20231003175006696](https://cdn.jsdelivr.net/gh/letengzz/tc2@main/img/Java/202310031750612.png)

![image-20231003175014065](https://cdn.jsdelivr.net/gh/letengzz/tc2@main/img/Java/202310031750199.png)

安装成功：

![image-20231003175041766](https://cdn.jsdelivr.net/gh/letengzz/tc2@main/img/Java/202310031750100.png)

配置依赖库 (`node_global`)：

- 创建node_global目录：

  ![image-20240507134716318](https://cdn.jsdelivr.net/gh/letengzz/tc2/img202405071347227.png)

- 设置依赖库：

  ```shell
  npm config set prefix "D:\ProGram\nodejs\node_global"
  ```

  ![image-20240507134811833](https://cdn.jsdelivr.net/gh/letengzz/tc2/img202405071348208.png)

- 查看设置成功：

  ```shell
  npm config get prefix
  ```

  ![image-20240507134824849](https://cdn.jsdelivr.net/gh/letengzz/tc2/img202405071348657.png)

- 设置环境变量：

  ![image-20240507135338168](https://cdn.jsdelivr.net/gh/letengzz/tc2/img202405071353541.png)

配置缓存 (`node_cache`)：

- 创建node_cache目录：

  ![image-20240507134929846](https://cdn.jsdelivr.net/gh/letengzz/tc2/img202405071349320.png)

- 设置依赖库：

  ```shell
  npm config set cache "D:\ProGram\nodejs\node_cache"
  ```

  ![image-20240507135116077](https://cdn.jsdelivr.net/gh/letengzz/tc2/img202405071351160.png)

- 查看设置成功：

  ```shell
  npm config get cache
  ```

  ![image-20240507135133580](https://cdn.jsdelivr.net/gh/letengzz/tc2/img202405071351017.png)

## 验证安装成功

Win+R 输入cmd，在cmd中输入 `node -v`

```bash
node -v
```

![image-20231003175215400](https://cdn.jsdelivr.net/gh/letengzz/tc2@main/img/Java/202310031752181.png)