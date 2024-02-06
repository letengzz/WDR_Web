# Node.js 安装

- [Windows 安装Node.js](Windows/README.md)
- [Mac 安装Node.js](Mac/README.md)

安装完成后，新建一个js文件并输入：

```js
console.log('hello Node.js');
```

![image-20231003181424364](https://cdn.jsdelivr.net/gh/letengzz/tc2@main/img/Java/202310031814817.png)

在CMD中输入：

```bash
node 文件名.js
```

![image-20231003181537604](https://cdn.jsdelivr.net/gh/letengzz/tc2@main/img/Java/202310031816614.png)

**注意**：

1. Node.js 中不能使用 BOM 和 DOM 的API (Node.js 并没有包含BOM 和 DOM)

   ![image-20231003181746154](https://cdn.jsdelivr.net/gh/letengzz/tc2@main/img/Java/202310031818515.png)

   ![image-20231003181816993](https://cdn.jsdelivr.net/gh/letengzz/tc2@main/img/Java/202310031818303.png)

   ```js
   //测试 以下命令 程序会报异常
   //BOM
   console.log(window);
   console.log(history);
   console.log(navigator);
   console.log(location);
   //DOM
   console.log(document);
   //AJAX
   let xhr = new XMLHttpRequest();
   ```

   ```js
   //测试 以下命令 程序不会报异常 正常输出
   console.log('1');
   
   setTimeout(() =>{
       console.log('love')
   },1000);
   ```

2. Node.js  的顶级对象并不是window对象 而是 global对象，也可以用globalThis 访问顶级对象

   ```js
   console.log(global);
   console.log(globalThis); 
   console.log(global == globalThis);//ES2020引入的新特性 用globalThis指向顶级对象 Node.js支持此特性
   ```

   