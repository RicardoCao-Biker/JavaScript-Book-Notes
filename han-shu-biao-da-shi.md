#### 函数表达式&函数声明

* 函数声明提升，在执行代码前先读取函数声明

* 递归时，如果对递归的函数进行了复制，同时将原函数设为null，那么递归会出错，此时可以使用arguments.callee\(\)来实现对正在执行函数的递归调用。


