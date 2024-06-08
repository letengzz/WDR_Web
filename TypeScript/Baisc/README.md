# TypeScript 基本使用

## 类型声明

类型声明是TypeScript非常重要的一个特点，通过类型声明可以指定TypeScript中变量（参数、形参）的类型。指定类型后，当为变量赋值时，TypeScript编译器会自动检查值是否符合类型声明，符合则赋值，否则报错。

简而言之，类型声明给变量设置了类型，使得变量只能存储某种类型的值

语法：

```typescript
let 变量: 类型;

let 变量: 类型 = 值;

function fn(参数: 类型, 参数: 类型): 类型{
    ...
}
```

## 自动类型判断

TypeScript拥有自动的类型判断机制。当对变量的声明和赋值是同时进行的，TypeScript编译器会自动判断变量的类型。所以如果变量的声明和赋值时同时进行的，可以省略掉类型声明。

## 类型断言

有些情况下，变量的类型是很明确，但是TS编译器却并不清楚，此时，可以通过类型断言来告诉编译器变量的类型。

断言有两种形式：

- 第一种：

  ```typescript
  let someValue: unknown = "this is a string";
  let strLength: number = (someValue as string).length;
  ```

- 第二种：

  ```typescript
  let someValue: unknown = "this is a string";
  let strLength: number = (<string>someValue).length;
  ```


## 联合类型

可以使用` | `来连接多个类型

```typescript
let b: "male" | "female";
b = "male";
b = "female";

let c: boolean | string;
c = true;
c = 'hello';
```

