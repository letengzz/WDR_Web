# Vite

Vite 是快速构建前端的脚手架

**官方网站**：https://cn.vitejs.dev

## 安装

`npm create vite@latest` 用于使用npm 包管理器创建一个vite项目

执行该命令会初始化一个新的项目，配置好必要的文件，并安装所有必要的依赖，包括安装好Vite本身(执行这个命令会自动安装Vite，不需要手动安装vite)

**注意**：Vite 需要 [Node.js](https://nodejs.org/en/) 版本 18+，20+。然而，有些模板需要依赖更高的 Node 版本才能正常运行，当包管理器发出警告时，请注意升级Node 版本。

**参数**：

- npm是Node Package Manager 的缩写，是Nodejs的包管理工具
- create是npm命令，用于创建新的npm包
- vite@latest 表示使用最新版本的vite

```shell
npm create vite&latest
```

提示：`Need to install the following packages`，输入y即可：

![image-20240602180008778](https://cdn.jsdelivr.net/gh/letengzz/tc2/img202406021800495.png)

输入：项目名、前端框架、编程语言即可

![image-20240602180205910](https://cdn.jsdelivr.net/gh/letengzz/tc2/img202406021802111.png)

按照提示：cd进入创建的项目 --> 安装项目依赖(npm install) --> 运行项目(npm run dev)

![image-20240602180311629](https://cdn.jsdelivr.net/gh/letengzz/tc2/img202406021803553.png)

访问：http://localhost:5173/

![image-20240602180353884](https://cdn.jsdelivr.net/gh/letengzz/tc2/img202406021803469.png)

## 更改配置

当以命令行方式运行 `vite` 时，Vite 会自动解析 项目根目录 下名为 `vite.config.js` 的配置文件 (支持其他 JS 和 TS 扩展名)。

### 设置端口号

使用`server.port`指定开发服务器端口。

**注意**：如果端口已经被使用，Vite 会自动尝试下一个可用的端口，所以这可能不是开发服务器最终监听的实际端口。

- **类型：** `number`
- **默认值：** `5173`

https://cn.vitejs.dev/config/server-options.html#server-port

```typescript
import { defineConfig } from 'vite'
import vue from '@vitejs/plugin-vue'

// https://vitejs.dev/config/
export default defineConfig({
  plugins: [vue()],
  server: {
    port: 9999 //设置端口号
  }
})
```

### 设置自动打开程序

使用`server.open`开启在开发服务器启动时，自动在浏览器中打开应用程序。当该值为字符串时，它将被用作 URL 的路径名。如果想在喜欢的某个浏览器打开该开发服务器，你可以设置环境变量 `process.env.BROWSER` （例如 `firefox`）。还可以设置 `process.env.BROWSER_ARGS` 来传递额外的参数（例如 `--incognito`）。

`BROWSER` 和 `BROWSER_ARGS` 都是特殊的环境变量，你可以将它们放在 `.env` 文件中进行设置。

- **类型：** `boolean | string`

官方教程：https://cn.vitejs.dev/config/server-options.html#server-open

```typescript
import { defineConfig } from 'vite'
import vue from '@vitejs/plugin-vue'

// https://vitejs.dev/config/
export default defineConfig({
  plugins: [vue()],
  server: {
    port: 9999, //设置端口号
    open: true, //设置自动打开浏览器
  }
})
```

### 配置IP地址

使用`server.host`指定服务器应该监听哪个 IP 地址。 如果将此设置为 `0.0.0.0` 或者 `true` 将监听所有地址，包括局域网和公网地址。

也可以通过 CLI 使用 `--host 0.0.0.0` 或 `--host` 来设置。

- **类型：** `string | boolean`
- **默认：** `'localhost'`

官方教程：https://cn.vitejs.dev/config/server-options.html#server-host

```typescript
import { defineConfig } from 'vite'
import vue from '@vitejs/plugin-vue'

// https://vitejs.dev/config/
export default defineConfig({
  plugins: [vue()],
  server: {
    port: 9999, //设置端口号
    open: true, //设置自动打开浏览器
    host: '0.0.0.0', //设置IP
  }
})
```

![image-20240602182623156](https://cdn.jsdelivr.net/gh/letengzz/tc2/img202406021826636.png)

### 配置@路径别名

path模块是node.js的内置模块。而node.js默认不支持ts文件，所以需要安装：

```shell
npm install @types/node --save-dev
```

修改vite.config.ts：

```typescript
import { defineConfig } from 'vite'
import vue from '@vitejs/plugin-vue'
import { resolve } from 'path'

// https://vitejs.dev/config/
export default defineConfig({
  plugins: [vue()],
  server: {
    port: 9999, //设置端口号
    open: true, //设置自动打开浏览器
    host: '0.0.0.0', //设置IP
  },
  resolve: {
    alias: [
      {
        find: '@',
        replacement: resolve(__dirname,'src')
      }
    ]
  }
})
```

在tsconfig.json配置：

```json
{
  "compilerOptions": {
	...
  
    "baseUrl": ".",
    "paths": {
      "@/*":[
        "src/*"
      ]
    }
  },
...
}
```

