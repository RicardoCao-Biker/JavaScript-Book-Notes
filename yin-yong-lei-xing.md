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
  * forEach\(\)   var newarr = arr.map\(function\(item,index,array\){return item\*2}\)
  * map\(\)   var newarr = arr.map\(function\(item,index,array\){return item\*2}\)


