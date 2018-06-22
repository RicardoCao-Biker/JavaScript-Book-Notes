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
* 字符串转换：toString\(\)方法，接受一个使用进制的参数，注意null和undefined值类型没有这个方法 。 如果需要将null和undefined也转为字符串可以使用string\(\)方法。
* Object类型： 
  * 属性：
    * constructor:构造函数
    * hasOwnProperty\(name\)检查当前对象实例中是否存在属性
    * isPropertyOf\(object\)检查传入的对象是否是当前对象的原型
    * toString\(\)返回字符串表示
    * valueOf\(\)返回最适合该对象类型的原始值

#### 操作符

* 一元操作符

  * 递增/递减：++ --

    * 前置 ： 变量的值在语句被求值以前改变的

    * 后置 ： 变量的值在语句求值后执行改变

* 位操作符 ： 用于处理二进制数据

  * ~按位非 &按位与 \|按位或

* 布尔操作符：与或非三种

  * 非：！ 首先会先将操作数转为布尔型然后执行取反

```
!"blue"  //false
!0 //true 
!NaN //true
!"" //true
!12345 //false
```

* * 与：&&  短路操作
  * 或： \|\| 
* 乘性操作符

  * 乘法 ： \*
  * 除法 ： /  如果被0除则返回Infinity
  * 余数： %

* 加性操作符

  * 加法 ： +  注意：如果有一个操作数是字符串，则将数值转为字符串并连接起来  5+"5" //"55\`
  * 减法 ： — 

* 关系操作符 &lt; &lt;=  &gt;= &gt;
  * 如果两个操作数都是字符串则比较字符串对应的字符编码值
  * 如果其中一个是数值，则将另一个操作数转为数值并比较

```
"23"<"3"    //true
"23"<3    //false
```

* 相等操作符
  * 相等和不相等 ==     !=,这两个操作会强制对操作数进行转型然后再比较，如果一个操作数是字符串另一个是数字，先将字符串转换为数值   注意：该操作符下null和undefined是相等的
  * 全等和不全等 ===    !==,不进行转型直接进行比较，不同数据类型不全等

```
null == undefined  //true
NaN != NaN    //true
true == 1 //true
true == 2 //false
undefined == 0 //false
null == 0 //false 
"5" == 5    //true
```

* 条件操作符（三元操作符）variable = boolean_expression ? true\_value : false\_value _

### 语句





