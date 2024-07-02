# TypeScript 基本类型

JavaScript 中的数据类型：string 、 number 、 boolean 、 null 、 undefined 、 bigint 、 symbol 、 object(包括：Array、Function、Date...)

TypeScript 中的数据类型：

1. JavaScript 所有数据类型
2. 四个新类型：void、never、unknown、 any、 enum、tuple
3. 自定义类型：type、 interface

TypeScript中的三个构造函数： Number 、 String 、 Boolean ，他们只用于包装对象，正常开发时，很少去使用他们。

![image-20240128233155908](https://cdn.jsdelivr.net/gh/letengzz/tc2/img202401282332924.png)

- number

  ```typescript
  let decimal: number = 6;
  let hex: number = 0xf00d;
  let binary: number = 0b1010;
  let octal: number = 0o744;
  let big: bigint = 100n;
  ```

- boolean

  ```typescript
  let isDone: boolean = false;
  ```

- string

  ```typescript
  let color: string = "blue";
  color = 'red';
  
  let fullName: string = `Bob Bobbington`;
  let age: number = 37;
  let sentence: string = `Hello, my name is ${fullName}.
  
  I'll be ${age + 1} years old next month.`;
  ```

- 字面量，也可以使用字面量去指定变量的类型，通过字面量可以确定变量的取值范围

  ```typescript
  let color: 'red' | 'blue' | 'black';
  let num: 1 | 2 | 3 | 4 | 5;
  ```

- any 表示的是任意类型，一个变量设置类型为any后相当于对该变量关闭了TS的类型检测，使用TS时，不建议使用any类型

  ```typescript
  let d: any = 4;
  d = 'hello';
  d = true;
  ```

  声明变量如果不指定类型，则TS解析器会自动判断变量的类型为any (隐式的any)

  ```typescript
  let d;
  d = 10;
  d = 'hello';
  d = true;
  ```

- unknown 表示未知类型的值

  ```typescript
  let notSure: unknown = 4;
  notSure = 'hello';
  let s:string;
  
  // d的类型是any，它可以赋值给任意变量
  // s = d;
  
  e = 'hello';
  
  // unknown 实际上就是一个类型安全的any
  // unknown类型的变量，不能直接赋值给其他变量
  if(typeof e === "string"){
      s = e;
  }
  ```

- void用来表示空

  ```typescript
  let unusable: void = undefined;
  function fn(): void{
  }
  ```

  没有返回值的函数

  ```ts
  function fn(): void{
  
  }
  ```

- never表示永远不会返回结果

  ```typescript
  function error(message: string): never {
    throw new Error(message);
  }
  ```

- object

  ```typescript
  let obj: object = {};
  ```

- array

  ```typescript
  let list: number[] = [1, 2, 3];
  let list: Array<number> = [1, 2, 3];
  ```

- tuple

  ```typescript
  let x: [string, number];
  x = ["hello", 10]; 
  ```

- enum

  ```typescript
  enum Color {
    Red,
    Green,
    Blue,
  }
  let c: Color = Color.Green;
  
  enum Color {
    Red = 1,
    Green,
    Blue,
  }
  let c: Color = Color.Green;
  
  enum Color {
    Red = 1,
    Green = 2,
    Blue = 4,
  }
  let c: Color = Color.Green;
  ```