#### 变量：基本类型/引用类型

* 基本类型：undefined、Null、Boolean、Number、String是按值访问的

* 引用类型：object按引用访问。

* 可以为引用类型添加属性，但是不能为基本类型添加属性。

* 变量值的复制：

```
var num1 = 5;
var num2 = num1;
//此时num1和num2各开了一块内存分别是独立的

var obj1 = new Object();
var obj2 = obj1;
obj1.name = 'rico';
alert(obj2.name); //'rico‘
//obj1和obj2都指向的相同的栈内存
```

* 传递参数：函数的参数是按值传递到，如果是基本类型会复制值给局部变量，如果是引用则会把内存中的地址赋值给局部变量。

```
fucntion setName(){
    obj.name = "rico";
    obj = new Object();
    obj.name = "hello";
}

var person = new Object();
setName(person);
alert(person.name)  //"rico",如果在函数内部重写object，这个变量引用的就是一个局部对象的，会在函数执行后销毁。
```



