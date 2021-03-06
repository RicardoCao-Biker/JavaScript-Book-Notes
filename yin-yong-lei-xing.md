#### object类型

* 创建Object实例的方法：
  * 使用new操作符

```
var a = new Object();
a.name = 'a';
```

* 使用对象字面量

```
var a = {
    name : 'a',
    age : '10'
}
```

* var person = {}   与 new Object\(\)相同
* 访问属性的方法
  * 使用.   ，除非设计变量访问属性，否则使用点表示法。
  * 使用\[\] ，此种方法允许使用变量访问属性。注意，应以字符串的形式访问属性，例如person\["name"\]

#### Array类型

* 数组的每一项可以保存任何类型的数据
* 创建Array：
  * 使用Array构造函数

```
var a = new Array();//可以在括号中指定数组长度、或者传入初始值
```

* * 数组字面量

```
var a = [1,2,3]
```

* 数组的length属性是可以设置的

* 检测数组：

  * if\(value instanceof Array\){}该中方法在页面中有多个框架时，一个框架向另一个框架传入数组则分别对应两个构造函数。

> ```
> object instanceof constructor
> ```
>
> ```
> instanceof 运算符用来检测 constructor.prototype 是否存在于参数 object 的原型链上。
> ```

* * if\(Array.isArray\(value\)\){}
* 转换方法：

  * toString\(\)      =&gt;  "arg1,arg2,arg3"
  * valueOf\(\)      =&gt;   \[arg1,arg2,arg3\]
  * join\(\)       =&gt;    arr.join\("\|\|"\)   =&gt;  arg1\|\|arg2\|\|arg3\|\|.....

* 栈方法：

  * push\(\) 返回修改后的长度,注意：push的一个参数对应数组的一个值，如果push的是一个数组，则数组进入新数组成为新数组的一个值。
  * pop\(\) 返回移除的项

* 队列方法：

  * shift\(\)取出第一项并返回   
  * unshift\(\)压入第一项

* 重排序方法：

  * reverse\(\) 翻转数组
  * sort\(\) 接受一个比较函数作为参数,比较函数接受两个参数，第一个参数大于第二个参数返回正，小于返回负，等于返回零

```
function compare(value1,value2){
    if(value1 < value2){
        return -1;
    }else if(value1 > value2){
        return 1;
    }else{
    return 0
    }
}

var values = [0,2,5,2];
values.sort(compare);
```

* 操作方法
  * concat\(\)     arr.concat\(arg1,arg2...\),注意：concat**创建一个新数组并返回，原数组不变**。同时，传入的参数无论是数组还是普通类型，如果是数组则将其拆开并入新数组。
  * slice\(\)   基于当前数组的项**创建新数组，原数组不变。**
  * splice\(起始位置,要删除的个数,要插入的项...\) ，返回值为删除的数组
* 位置方法：

  * indexOf\(\) :接受两个参数，要查找的项 和 查找起点位置。
  * lastIndexOf\(\)

* 迭代方法：不修改原数组的值

  * every\(\) 必须每个项都满足条件才返回true

  * some\(\) 有一项满足就返回true

  * filter\(\)   var newarr = arr.filter\(function\(item,index,array\){return item &gt; 2}\)

  * forEach\(\)   arr.forEach\(function\(item,index,array\){do something}\)    //没有返回值

  * map\(\)   var newarr = arr.map\(function\(item,index,array\){return item\*2}\)

* 归并方法：

  * reduce\(\)   var sum = arr.reduce\(function\(prev,cur,index,array\){return prev + cur}\)  累加

#### Date类型

* 创建日期对象：  var now = new Date\(\);

* 获取时间差

```
var start = Date.now();
doSomething();
var stop = Data.now();
var result = stop - start ; //时间差毫秒数
```

* 方法：
  * getTime\(\)  日期的毫秒数
  * getFullYear\(\)
  * getMonth\(\)
  * getDate\(\)
  * getDay\(\)  星期数
  * getHours\(\)
  * getMinutes\(\)
  * getSeconds\(\)

#### Function类型

* 没有重载：同名函数，后声明覆盖前声明
* 函数声明提升

  * 函数声明会在代码执行之前就将函数声明添加到执行环境中   function a\(\){}
  * 函数表达式要在执行时才声明。   var a = function\(\){}

* 函数可以作为值传递。

* 函数内部属性

  * arguments：类数组对象，包含传入函数的所有参数。注意arguments的一个callee的属性，指向拥有该arguments对象的函数。在递归调用中，为了避免函数名发生变化导致递归调用的函数名也需要变，可以使用arguments.callee来代替函数名。
  * this，this引用的是函数执行的环境对象。

* 函数属性和方法：

  * 两个属性：length和prototype，length为函数的参数个数
  * 方法：
    * apply\(\) 第一个参数为运行函数的作用域，第二个为参数数组
    * call\(\)  第二个参数开始为逐个列举的参数
    * bind\(\)  会创建一个函数的实例，其this指向被绑定的值，后续直接调用函数也会直接指向绑定的作用域。

#### 基本包装类型

* 基本类型的属性和方法只存在于创建的一行代码的瞬间，然后立即被销毁，故不可以为基本类型添加属性和方法。

* 不要使用Boolean对象，因为Boolean对象在判断等情况下与基本类型的Boolean有出入，容易造成误解。

* 不建议使用实例化的Number\(\) 类型

* String类型的方法：

  * str.charAt\(index\) 用于访问指定位置的字符串/ str\[index\] 也可以同样完成功能，需要浏览器支持

* * concat\(\) 返回新的字符串   var newstr = oldstr.concat\(arg1,arg2 ....\)，实践中建议使用+号进行字符串拼接
  * slice\(\) /subString\(\) 截取生成新字符串，原字符串不变。
* * 字符串为位置方法：
    * indexOf\(\),接受两个参数，第二个参数为从参数值位置开始查找
    * lastIndexOf\(\)
* * trim\(\) 创建一个字符串副本，并删除前置和后缀的所有空格。
  * 大小写转换toLowerCase\(\) /toUpperCase.
  * match\(\)匹配   text.match\(pattern\)    text.search\(pattern\)
  * replace\(\)方法接受两个参数，第一个参数为字符串或正则表达式，如果为字符串则只会替换第一个字符串，第二个参数可以为字符串或函数。等
  * split\(\),第一个参数为指定的分隔符，该方法会按照分隔符最字符串进行分隔，并依次push进数组中。

#### 单体内置对象

* eval\(\) 类似一个ES解析器，只接受一各参数，即要执行的ES代码字符串，eval中声明的变量不会提升，只有在eval执行时才会创建。
* window对象，在全局中声明的所有变量和函数，都成为了window对象的属性。
* Math对象
  * Math.max\(arg1,arg2...\)
  * Math.min\(arg1,arg2...\)
  * Math.ceil\(\)向上舍入
  * Math.floor\(\)向下舍入
  * Math.round\(\)四舍五入
  * Math.random\(\)返回0-1的随机数

#### 题目：

```
function foo(){
	this.value = 42;
};
console.log(foo.prototype);
foo.prototype.rico = '123';
console.log(foo.prototype);
foo.prototype = {
	method: function(){return true;}
};
console.log(foo.prototype);
function bar(){
	return{
		ni : function(){},
		method: function(){return value;}
	};
};
foo.prototype = new bar();
console.log(foo.prototype);
console.log(foo.prototype instanceof bar);
var test = new foo();
console.log(test instanceof foo);
console.log(test instanceof bar);
VM1120:4 {constructor: ƒ}
VM1120:6 {rico: "123", constructor: ƒ}
VM1120:10 {method: ƒ}
VM1120:18 {ni: ƒ, method: ƒ}
VM1120:19 false
VM1120:21 true
VM1120:22 false
```



