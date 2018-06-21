### 语法

* ECMAScript中的一切：变量、函数名、操作符都区分大小写

* 严格模式：  在顶部或function内部添加`"use strict";`

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

* Null类型：如果变量准备用于保存对象，最好将变量初始化为null，这样可以通过判断变量是否为null确认变量是否保存了对象。

  * 显式赋值为null是有意义的，显式赋值为undefined是无意义的

    * console.log\(undefined===null\) //false

    * console.log\(undefined==null\) //true

* Boolean类型：
  * | 数据类型 | true | false |
    | :--- | :--- | :--- |
    | string | 非空字符串 | ""  空字符串 |
    | number | 非零数字值 | 0 和 NaN |
    | object | 任何对象 | null |

* Number类型：
  * 浮点数值：包含小数点   浮点数值的计算精度较弱， 0.1 + 0.2  == 0.3 //false
  * 如果浮点数数值本身为整数，则会被自动转换为不带浮点的整数。   10.0   =&gt;   10
  * NaN用来表示本来要返回数值的操作未返回数值, alert\(NaN == NaN\) //false
    * isNaN\(\)方法用来测试 是否不是数值 ，注意特例： isNaN\("12"\) //false 可以被转换成数值   isNaN\("blue"\) //true 无法转换成数值
* 数值转换：非数值转换为数值使用方法 parseInt\(\),接受两个参数，第一个参数为被转换的值，第二个参数为使用的进制。parseFloat\(\) 用来处理浮点数值转换，遇到第一个小数点是会自动保留。

```
parseInt("AF",16) //175
parseInt("AF") //NaN
parseFloat("22.34.5") //22.34
```

* String类型： 字符串一旦创建，它的值是不可以更改的，只能通过重新赋值。
* 字符串转换：toString\(\)方法，接受一个使用进制的参数，注意null和undefined值类型没有这个方法



