# TypeScript 面向对象

**声明函数参数**：

```typescript
// 参数x必须是数字，参数y也必须是数字，函数返回值也必须是数字
function demo(x:number,y:number):number{
 return x + y
}
demo(100,200)
demo(100,'200') //警告：类型“string”的参数不能赋给类型“number”的参数
demo(100,200,300) //警告：应有 2 个参数，但获得 3 个
demo(100) //警告：应有 2 个参数，但获得 1 个
```

## 泛型

定义⼀个函数或类时，有些情况下⽆法确定其中要使⽤的具体类型（返回值、参数、属性的类型不能确定），此时就需要泛型了

 `<T>` 就是泛型 (不⼀定非叫 T )，设置泛型后即可在函数中使用 T 来表示该类型：

```typescript
function test<T>(arg: T): T{
return arg;
}
// 不指名类型，TS会⾃动推断出来
test(10)
// 指名具体的类型
test<number>(10)
```

泛型可以写多个：

```typescript
function test<T, K>(a: T, b: K): K{
 return b;
}
// 为多个泛型指定具体⾃值
test<number, string>(10, "hello");
```

类中同样可以使⽤泛型：

```typescript
class MyClass<T>{
 prop: T;
 constructor(prop: T){
 this.prop = prop;
 }
}
```

也可以对泛型的范围进⾏约束：

```typescript
interface Demo{
 length: number;
}
// 泛型T必须是MyInter的⼦类，即：必须拥有length属性
function test<T extends Demo>(arg: T): number{
 return arg.length;
}
test(10) // 类型“number”的参数不能赋给类型“Demo”的参数
test({name:'张三'}) // 类型“{ name: string; }”的参数不能赋给类型“Demo”的参数
test('123')
test({name:'张三',length:10})
```

