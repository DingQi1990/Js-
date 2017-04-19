# 基础问题

## 简述

首先学习Node.js .要基础开始学习,要给基础打牢才能在接下来的学习中如鱼得水,所以我先从基础问题开始学习,首先Node.js与前端js不同,Node.js 主要是操作一些后台,数据库,所以哪些DOM操作基本还少接触,后端几乎是直面服务器内存的,更加偏向内存方面,所以基础问题很重要.

##### 类型判断

Javascript 的类型判断这里要提到一个词就是有 Typescri, 那什么是Typescri ? **TypeScript**是一种由微软开发的自由和[开源](http://baike.baidu.com/item/%E5%BC%80%E6%BA%90)的编程语言。它是[JavaScript](http://baike.baidu.com/item/JavaScript)的一个超集而且本质上向这个语言添加了可选的静态类型和基于类的[面向对象编程].TypeScript扩展了[JavaScript](http://baike.baidu.com/item/JavaScript)的语法，所以任何现有的JavaScript程序可以不加改变的在TypeScript下工作。TypeScript是为大型应用之开发而设计，而编译时它产生 JavaScript 以确保兼容性。

##### 作用域

说道作用域,一般会问到es6 中 let 与 var的区别.

首先需要明确的是let、const、var都是用来定义变量的 
在ES6之前，我们一般都用var来定义变量，例如 ：

```
function test(){

    var i=1;

    console.log(i);

    console.log(j);

    var j=2;

}

test();

console.log(i);

```

在上面的代码中，我们可以预计到第一个console输出的是1，第二个由于变量提升输出的是undefine,而不是产生ReferenceError错误，第三个输出的还是1；也就是说在函数中定义的一个变量，在函数外部仍然是可以使用的，那么我们再来看看这一段代码：

```
function test(){
    let i=1;
    console.log(i);
    console.log(j);
    let j=2;
}
test();
console.log(i);
```

执行完后，我们会发现第一个console仍然输出了1，第二个和第三个产生了ReferenceError错误！对比之下我们会发现let的作用域比var更加严格了，有点类似于[Java](http://lib.csdn.net/base/javase)中的变量定义，1、必须先定义再使用，2、有着严格的作用域，变量只作用域当前隶属的代码块.

在新的ES6标准中let完全可以替代var,在ES6中另外一个定义变量的关键字是 const,const 代表一个值的 常量索引 ，也就是说，变量名字在内存中的指针不能够改变，但是指向这个变量的值 可能 改变。例如：

```
const names=[] ;
names.push(“1”) ;
console.log (names) ;
```

我们创建了一个拥有常量索引的数组变量，然后添加值到这个数组中，但是并不改变它的索引，所以上面的代码完全可以运行。 





##### 内存释放

引用类型是在没有引用之后, 通过 v8 的 GC 自动回收, 值类型如果是处于闭包的情况下, 要等闭包没有引用才会被 GC 回收, 非闭包的情况下等待 v8 的新生代 (new space) 切换的时候回收.

与前端 Js 不同, 2年以上经验的 Node.js 一定要开始注意内存了, 不说对 v8 的 GC 有多了解, 基础的内存释放一定有概念了, 并且要开始注意内存泄漏的问题了.所以说内存对于考研一个程序员对Node.js的理解非常重要.



##### ES6 新特性

我们需要掌握箭头函数与 function 的区别.

首先箭头函数中的 this 确实和调用时的上下文无关.

箭头函数都是十分单纯的沿着作用域链向上寻找……

箭头函数不可以当作构造函数，也就是说，不可以使用new命令，否则会抛出一个错误。

箭头函数不可以使用arguments对象，该对象在函数体内不存在。如果要用，可以用Rest参数代替。

我们还需要掌握什么是闭包?

**闭包是指有权限访问另一个函数作用域的变量的函数**，创建闭包的常见方式就是在一个函数内部创建另一个函数.这个问题经常会在面试中提问.