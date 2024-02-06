# Mac 安装Node.js

打开 [Node.js官网](http://nodejs.org) 下载Node.js

- Node.js 官网：http://nodejs.org
- Node.js 中文站下载：http://nodejs.cn/download
- Node.js 历史版本：https://registry.npmmirror.com/binary.html?path=node

**注意**：

- LTS：长期支持版本
- Current：最新版

![image-20240206175117731](https://cdn.jsdelivr.net/gh/letengzz/tc2@main/imgimage-20240206175117731.png)

也可以通过 https://nodejs.org/en/download 下载

![image-20240206175357575](https://cdn.jsdelivr.net/gh/letengzz/tc2@main/imgimgimage-20240206175357575.png)

下载完毕后，双击安装Node.js

![image-20240206175416170](https://cdn.jsdelivr.net/gh/letengzz/tc2@main/imgimage-20240206175416170.png)

![image-20240206175445639](https://cdn.jsdelivr.net/gh/letengzz/tc2@main/imgimage-20240206175445639.png)

![image-20240206175513631](https://cdn.jsdelivr.net/gh/letengzz/tc2@main/imgimage-20240206175513631.png)

安装成功：

![image-20240206175548048](https://cdn.jsdelivr.net/gh/letengzz/tc2@main/imgimage-20240206175548048.png)

环境配置：打开Mac 终端，配置全局环境变量，键盘输入 `vim .bash_profile`进入编辑状态，打开之后添加一行代码：`PATH=$PATH:/usr/local/bin/`。点击 esc 退出编辑状态，此时无法对内容进行修改。键盘输入 `:wq!` 强制保存并退出vim，回到终端的界面

## 验证安装成功

在Mac 终端，键盘输入 `node -v`验证安装成功：

```bash
node -v
```

![image-20240206180351876](https://cdn.jsdelivr.net/gh/letengzz/tc2@main/imgimage-20240206180351876.png)