#### 接口

```js
// 类型约束
interface Person {
  firstName: string;
  lastName: string;
  age: number;
}
```

```js
// 对象的属性索引
interface A {
  [prop: string]: number;
}
// 对象的方法
// 写法一
interface A {
  f(x: boolean): string;
}

// 写法二
interface B {
  f: (x: boolean) => string;
}

// 写法三
interface C {
  f: { (x: boolean): string };
}
```
####   继承
```js
interface Shape {
  name: string;
}
interface Circle extends Shape {
  radius: number;
}
interface Circle extends Style, Shape {
  radius: number;
}

// interface 可以继承type命令定义的对象类型。
// type命令定义的类型不是对象，interface 就无法继承
type Country = {
  name: string;
  capital: string;
}

interface CountryWithPop extends Country {
  population: number;
}
// interface 继承 class
```
#### interface 与 type 的异同

- type能够表示非对象类型，而interface只能表示对象类型（包括数组、函数等）。
- interface可以继承其他类型，type不支持继承。