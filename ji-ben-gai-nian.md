### 语法

* ECMAScript中的一切：变量、函数名、操作符都区分大小写

* 严格模式：  在顶部或function内部添加` "use strict";`
* 代码块使多条语句组合到一个代码块中，代码块通过`{A;B;}`开头和结尾。

#### 关键字

* 作用：表示控制语句的开始或结束或用于执行特定操作。

```
vbreak do instanceof typeof case else new var catch finally return void continue for switch while debugger
function this with default if throw delete in try
```

#### 变量

* 使用var定义变量，如果未初始化则变量值为 undefined

```
var a = 'hi';
a = 100 ; //这样修改变量的类型是不会报错的
```

* 在function中var定义的变量会成为该function的局部变量，在函数退出后局部变量会被销毁。

* 如果省略var关键字直接声明变量，则该变量为全局变量。

```
function test(){
    a = 'hi' //全局变量
}
test();//在调用过一次test后，a变量就有了定义，可以在全局被访问到
```

* 可以使用一个var关键字同时声明多个不同类型的变量，赋值语句之间使用逗号隔开。

### 数据类型

```
undefined null boolean number string object symbol
```

* typeof操作符：
  * undefined 未定义
  * boolean 布尔值
  * number数值
  * string字符串
  * object对象或NULL（NULL值为空对象的引用，故null为object类型）
  * function函数

```
var a;
alert(typeof a);//undefined
alert(typeof b);//undefined (因为未初始化的变量会自动被赋予undefined值)
```

* null类型：如果变量准备用于保存对象，最好将变量初始化为null，这样可以通过判断变量是否为null确认变量是否保存了对象。

* 显式赋值为null是有意义的，显式赋值为undefined是无意义的

* console.log\(undefined===null\) //false
* console.log\(undefined==null\) //true



