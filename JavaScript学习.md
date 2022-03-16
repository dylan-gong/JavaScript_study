# 1、什么是JavaScript

## 1.1、概述

JavaScript是一门世界上最流行的脚本语言

Java，JavaScript

只用10天就开发出来了

==一个合格的后端人员需要精通JavaScript==

## 1.2、历史

ECMAScript它可以理解为是JavaScript的一个标准

最新版本已经到es6版本~

但是大部分浏览器还只停留在支持es5代码上！
开发环境--线上环境，版本不一致



# 2、快速入门

## 2.1、引入JavaScript

### 1、内部标签

```html
<script>
    
    //......
    
    </script>
```



### 2、外部定义

abs.js

```html
//.....
```

Test.html

```html
<script src='abs.js'></script>
```



测试代码

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
<!--  Script标签内，写JavaScript代码-->
<!--  <script>-->
<!--    alert('hello,world!');-->

<!--  </script>-->

<!--  外部引入-->
<!--  注意：script标签必须成对出现-->
  <script src="js/dylan.js"></script>

<!--不用显示定义type，默认就是JS-->
  <script type="application/javascript"></script>

</head>
<body>
hello，world

<!--这里也可以存放JavaScript代码-->
</body>
</html>
```

## 2.2、基本语法入门

```html
<script>

<!--      JavaScript严格区分大小写-->
    // 1、定义变量  变量类型  变量名 = 变量值
    var score = 100;
    var name = "dylan";
    // 2、条件控制
    if(score>60 && score<70){
        alert("60-70");
        } else if(score>70 && score<80){
            alert("70-80");
        } else{
            alert("A plus")
        }

    // console.log(score)：在浏览器的控制台打印一个变量  相当于System.out.printf();

  </script>
```





==浏览器必备调试须知==

![image-20220309163404852](typora%E4%BF%9D%E5%AD%98%E7%9A%84%E5%9B%BE%E7%89%87/image-20220309163404852.png)







## 2.3、数据类型

数值，文本，音频，图片



==变量==

不能用数字开头

```javascript
var 王者用药 = "倔强青铜";
```



==number==

js不区分小数和整数，Number

```javascript
123//整数123
123.1//浮点数
1.234e3//科学计数法
-99//复数
NaN// not a number
Infinity //无限大
```



==字符串==

‘abc’，"abc"



==布尔值==

True, False





==逻辑运算==

```
&&  两个都为真，结果为真

||  一个为真，结果为真

!  真即假，假即真
```





==比较运算符==！！！！！！！！重要！！！！‼️



```
=  赋值符号

==  等于（类型不一样，值一样也会判断为true）

===  绝对等于（类型一样，值一样，结果才为true）
```

坚决不能使用 == 进行比较

+ NaN 这个与所有的数值都不相等，包括自己
+ 只能通过isNaN（NaN）来判断这个数是否是NaN



浮点数问题

```javascript
console.log((1/3) === (1-2/3))  //false
```

尽量避免使用浮点数运算，存在精度问题

```javascript
console.log(Math.abs(1/3-(1-2/3))<0.0000000000001); //ture
```



==null和undefined==

+ null 空
+ undefined 未定义



==数组==

一系列相同类型的对象

java的数组必须是相同类型的对象，JS中不需要

```javascript
var arr = [1,2,3,4,5,'hello',null,true];
```



取数组下标，如果越界了就会undefined



==对象==

对象是大括号，数组是中括号

每个属性之间用,隔开，最后一个不用加

```javascript
// Person person = new person(1,2,3,4,5);
      var person = {
          name:'qinjiang',
          age:3,
          tags:['js','java','web','...']
      };
```

取对象的值

```bash
person.name
> "qinjiang"

person.age
> 3
```



## 2.4、严格检查模式

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
  <script>

// 前提：IEDA要设置ES6语法
// 'use strict'：严格检查模式，预防JavaScript的随意性导致产生一些问题
// 局部变量建议都使用let去定义～
// 必须写在JS 第一行

   'use strict'
    // 全局变量
    i = 1;//在严格检查模式下，该语句是错误的。尽量避免使用这样的定义方式
      
    let i =1;
    //ES6 一般用let去定义

  </script>

</head>
<body>

</body>
</html>
```



# 3、数据类型

## 3.1、字符串

### 1、正常字符串我们使用单引号或者双引号包裹

### 2、注意转义字符（\）

```
\'
\n
\t
\u4e2d   \u####  unicode字符
\x41  Ascii字符
```

### 3、多行字符串编写

```javascript
// tab上面，esc下面  ``
var msg = `hello world
nihao
你好呀
哈哈哈`;
```

### 4、模板字符串

```javascript
let name = 'qianjiang';
let age = 3;

let msg = `你好呀，${name}`;
```

### 5、字符串长度

```javascript
console.log(student.length)
```

### 6、字符串的可变性，不可变

![image-20220314194944226](typora%E4%BF%9D%E5%AD%98%E7%9A%84%E5%9B%BE%E7%89%87/image-20220314194944226.png)



### 7、大小写转换

```javascript
//注意这里是方法，不是属性了
console.log(student.toUpperCase());//大写
console.log(student.toLowerCase());//大写
```

### 8、找下标

```javascript
console.log(student.indexOf('u'))
```

### 9、subString

```javascript
//[ )
console.log(student.substring(1)); //从第一个字符串截取到最后一个
console.log(student.substring(1,3)); //[1,3) 取前面不取后面
```



## 3.2、数组

==Array可以包含任意数据类型==

```javascript
var arr = [1,2,3,4,5];
arr[0]
arr[0] = 1;
```

### 1、长度

==注意：假如给arr.length赋值，数组大小就会发生变换~，如果赋值过小，元素就会丢失==

```javascript
arr.length
```

### 2、indexOf

==通过元素获得下标索引==

```JAVA
arr.indexOf(2);
1
```

**字符串的“1”和数字“1”是不同的**

### 3、slice()  

==截取数组的一部分，返回一个新的数组，类似于String中的subString==

### 4、push，pop

```
push：压入到尾部
pop：弹出尾部的一个元素
```

### 5、unshift()，shift()头部

```
unshift：压入到头部
shift：弹出头部的一个元素
```



###6、排序arr.sort()

![image-20220314203441246](typora%E4%BF%9D%E5%AD%98%E7%9A%84%E5%9B%BE%E7%89%87/image-20220314203441246.png)





### 7、元素反转 arr.reverse()

![image-20220314203503173](typora%E4%BF%9D%E5%AD%98%E7%9A%84%E5%9B%BE%E7%89%87/image-20220314203503173.png)





### 8、元素拼接  arr.concat()

==注意：concat()并没有修改数组，只是会返回一个新的数组==

![image-20220314203640436](typora%E4%BF%9D%E5%AD%98%E7%9A%84%E5%9B%BE%E7%89%87/image-20220314203640436.png)





### 9、连接符 arr.join();

==打印拼接数组，使用特定的字符串连接==

![image-20220314203805487](typora%E4%BF%9D%E5%AD%98%E7%9A%84%E5%9B%BE%E7%89%87/image-20220314203805487.png)





### 10、多维数组

![image-20220314203957181](typora%E4%BF%9D%E5%AD%98%E7%9A%84%E5%9B%BE%E7%89%87/image-20220314203957181.png)



==数组：存储数据（如何存，如何取，方法都可以自己实现）==





## 3.3、对象

若干个键值对

```javascript
var 对象名{
    属性名：属性值，
    属性名：属性值，
    属性名：属性值
}

var person = {
        name:"Tangshan",
        age:3,
        email:"791923285@qq.com",
        score:0
    }
```

==js中的对象。{......}表示一个对象，键值对描述属性xxxx：xxxx，多个属性之间用逗号隔开，最后一个属性不加逗号==

==JavaScript中的所有的键都是字符串，值是任意对象==

### 1、对象赋值

![image-20220314213111063](typora%E4%BF%9D%E5%AD%98%E7%9A%84%E5%9B%BE%E7%89%87/image-20220314213111063.png)



### 2、使用一个不存在的对象属性，不会报错！undefined

![image-20220314213140701](typora%E4%BF%9D%E5%AD%98%E7%9A%84%E5%9B%BE%E7%89%87/image-20220314213140701.png)

### 3、动态的删减属性

==通过delete删除对象属性==

![image-20220314213319820](typora%E4%BF%9D%E5%AD%98%E7%9A%84%E5%9B%BE%E7%89%87/image-20220314213319820.png)



### 4、动态的添加

![image-20220314213637533](typora%E4%BF%9D%E5%AD%98%E7%9A%84%E5%9B%BE%E7%89%87/image-20220314213637533.png)



### 5、判断属性值是否在这个对象中

==xxx in xxx==

![image-20220314213938901](typora%E4%BF%9D%E5%AD%98%E7%9A%84%E5%9B%BE%E7%89%87/image-20220314213938901.png)



### 6、判断一个属性是否是这个对象自身拥有的

![image-20220314214024222](typora%E4%BF%9D%E5%AD%98%E7%9A%84%E5%9B%BE%E7%89%87/image-20220314214024222.png)





## 3.4、流程控制

### 1、if判断

![image-20220314214428229](typora%E4%BF%9D%E5%AD%98%E7%9A%84%E5%9B%BE%E7%89%87/image-20220314214428229.png)



### 2、while循环，避免程序死循环

![image-20220314214631531](typora%E4%BF%9D%E5%AD%98%E7%9A%84%E5%9B%BE%E7%89%87/image-20220314214631531.png)

### 3、for循环

![image-20220314214838526](typora%E4%BF%9D%E5%AD%98%E7%9A%84%E5%9B%BE%E7%89%87/image-20220314214838526.png)



### 4、数组循环  forEach循环

![image-20220314215245695](typora%E4%BF%9D%E5%AD%98%E7%9A%84%E5%9B%BE%E7%89%87/image-20220314215245695.png)



### 5、for...in

![image-20220314215714680](typora%E4%BF%9D%E5%AD%98%E7%9A%84%E5%9B%BE%E7%89%87/image-20220314215714680.png)



### 6、for of

![image-20220315190919957](typora%E4%BF%9D%E5%AD%98%E7%9A%84%E5%9B%BE%E7%89%87/image-20220315190919957.png)

## 3.5、Map和Set

> ES6的新特性~

**Map:**

![image-20220314221511135](typora%E4%BF%9D%E5%AD%98%E7%9A%84%E5%9B%BE%E7%89%87/image-20220314221511135.png)



**Set:无序不重复集合**

![image-20220314221519606](typora%E4%BF%9D%E5%AD%98%E7%9A%84%E5%9B%BE%E7%89%87/image-20220314221519606.png)



## 3.6、iterator

### 1、遍历Map

![image-20220315191200764](typora%E4%BF%9D%E5%AD%98%E7%9A%84%E5%9B%BE%E7%89%87/image-20220315191200764.png)



### 2、遍历set

![image-20220315191212888](typora%E4%BF%9D%E5%AD%98%E7%9A%84%E5%9B%BE%E7%89%87/image-20220315191212888.png)





## 4、函数

### 4.1、定义一个函数

绝对值函数

```javascript
function abs(x){
    if(x>0){
        x;
    }else{
        return -x;
	}
}
```

==一旦执行到return代表函数结束，返回结果！==

==如果没有执行return，函数执行完也会执行返回结果，结果就是undefined或者NaN==

> 定义方式二

```javascript
var abs = function(x){
	if(x>0){
        x;
    }else{
        return -x;
	}
}
```

==function（x）{......}这是一个匿名函数。但是可以吧结果赋值给abs，通过abs就可以调用函数！==

**方式一方式二等价**

> 调用函数

```javas
abs(10) //10
abs(-10) //10
```

==参数问题：JavaScript可以传人一个参数，也可以不传参数==

> 假设不存在参数，如何规避？ -->手动抛出异常

![image-20220315192928989](typora%E4%BF%9D%E5%AD%98%E7%9A%84%E5%9B%BE%E7%89%87/image-20220315192928989.png)



> arguments

`arguments`是一个JS免费赠送的关键字

代表,传递进来的所有参数,是一个数组



问题:arguments包含所有的参数,我们有时候想使用多余的参数来进行附加操作. 需要排数已有参数

> rest

ES6引入的新特性,获取除了已经定义的参数之外的所有参数~      ...(可变长参数)

==以前:==

![image-20220315194323163](typora%E4%BF%9D%E5%AD%98%E7%9A%84%E5%9B%BE%E7%89%87/image-20220315194323163.png)



==现在:==

```JavaScript
function aaa(a,b,...rest) {
    console.log("a=>"+a);
    console.log("b=>"+b);
    console.log(rest);
}
```

rest参数只能写在最后面,必须用...标识



## 4.2、变量的作用域

在JavaScript中,var定义的变量实际是有作用域的

假设在函数体中的声明,则在函数体外不可以使用~ 非要使用可以研究使用`闭包`

![image-20220315202225382](typora%E4%BF%9D%E5%AD%98%E7%9A%84%E5%9B%BE%E7%89%87/image-20220315202225382.png)



==如果两个函数使用的相同的变量名,只要在函数内部,就不冲突==

![image-20220315202546752](typora%E4%BF%9D%E5%AD%98%E7%9A%84%E5%9B%BE%E7%89%87/image-20220315202546752.png)



==内部函数可以访问外部函数的成员,反之则不行==

![image-20220315202732622](typora%E4%BF%9D%E5%AD%98%E7%9A%84%E5%9B%BE%E7%89%87/image-20220315202732622.png)



==假设,内部函数变量和外部函数变量重名==

![image-20220315203800243](typora%E4%BF%9D%E5%AD%98%E7%9A%84%E5%9B%BE%E7%89%87/image-20220315203800243.png)



假设在JavaScript中,函数查找变量,从自身函数开始,由内向外查找,假设外部存在这个同名的函数变量,则内部函数会屏蔽外部函数

> 提升变量的作用域

![image-20220315204457386](typora%E4%BF%9D%E5%AD%98%E7%9A%84%E5%9B%BE%E7%89%87/image-20220315204457386.png)



`说明:JavaScript执行引擎,自动提升了y的声明,但是不会提升y的赋值  习惯:把所有变量定义在函数最前面,不要乱放,便于代码维护`

![image-20220315204751075](typora%E4%BF%9D%E5%AD%98%E7%9A%84%E5%9B%BE%E7%89%87/image-20220315204751075.png)



> 全局函数

![image-20220315205746612](typora%E4%BF%9D%E5%AD%98%E7%9A%84%E5%9B%BE%E7%89%87/image-20220315205746612.png)



全局对象 window



alert()这个函数本身也是一个`window`的变量

![image-20220315210446878](typora%E4%BF%9D%E5%AD%98%E7%9A%84%E5%9B%BE%E7%89%87/image-20220315210446878.png)





JavaScript实际上只有一个全局作用域,任何一个变量(函数也可视为变量),假设没有在函数作用范围内找到,就会向外查找;如果在全局作用域都没找到,报错`ReferenceError`



> 规范:由于我们全局所有的变量都会绑定到我们的window上.    如果不同的JavaScript文件,使用了相同的全局变量,如何能够减少冲突?

![image-20220315211125597](typora%E4%BF%9D%E5%AD%98%E7%9A%84%E5%9B%BE%E7%89%87/image-20220315211125597.png)



把自己的代码全部放到自己定义的唯一空间名字中,降低全局命名冲突的问题~   -->jQuery



> 局部作用域

![image-20220315211456269](typora%E4%BF%9D%E5%AD%98%E7%9A%84%E5%9B%BE%E7%89%87/image-20220315211456269.png)



**`ES6 let关键字,解决局部作用域冲突`**

![image-20220315211553578](typora%E4%BF%9D%E5%AD%98%E7%9A%84%E5%9B%BE%E7%89%87/image-20220315211553578.png)



**建议大家都使用`let`去定义局部作用域的变量;**



> 常量const

在ES6之前,怎么定义常量:只有用全部大写命名的变量就是常量;建议不要修改这样的词

![image-20220315211921926](typora%E4%BF%9D%E5%AD%98%E7%9A%84%E5%9B%BE%E7%89%87/image-20220315211921926.png)



在ES6引入了常量关键字:`const`

```JavaScript
const PI = '3.14'; // 只读变量
console.log(PI);
PI = '123'; // TypeError: Assignment to constant variable.
console.log(PI);
```



## 4.3、方法

> 定义方法

方法就是把函数放在对象里面,对象只有两个东西:属性和方法

```JavaScript
var kuangshen = {
    name: '秦疆',
    bitrh: 2000,
    age: function () {
        // 今年-出生的年
        let now = new Date().getFullYear();
        return now-this.bitrh;
    }
};

//属性
kuangshen.name
//方法,一定要带()
kuangshen.age()
```

> this.代表什么?

```JavaScript
function getAge() {
    // 今年 - 出生的年
    let now = new Date().getFullYear();
    return now-this.bitrh;
}

let kuangshen = {
    name: '秦疆',
    bitrh: 2000,
    age: getAge
};

// kuangshen.age()  调用成功
//getAge() NaN window
```

this是无法指向的,是默认指向调用它的那个对象



> apply

在JavaScript中可以控制this指向

```JavaScript
function getAge() {
    // 今年 - 出生的年
    let now = new Date().getFullYear();
    return now-this.bitrh;
}

let kuangshen = {
    name: '秦疆',
    bitrh: 2000,
    age: getAge
};

let xiaoming = {
    name: '小茗',
    bitrh: 2000,
    age: getAge
};

// kuangshen.age()  调用成功

getAge.apply(xiaoming,[]);// this，指向了 kuangshen这个对象，参数为空([])
```



# 5、对象

> 标准对象

>  `number`   `String`   `boolean`   `object`   `function`   `undefined` 





## 5.1、Date

**基本使用**

```JavaScript
let now = new Date(); //Sat Jan 04 2020 10:47:06 GMT+0800 (中国标准时间)
now.getFullYear(); //年
now.getMonth(); // 月   0~11  代表月
now.getDate(); // 日
now.getDay(); // 星期几
now.getHours(); // 时
now.getMinutes(); // 分
now.getSeconds(); // 秒

now.getTime(); // 时间戳 全世界统一 1970 1.1 0:00:00  毫秒数

console.log(new Date(1647405871460)) //时间戳转为时间
```



转换

```JavaScript
now = new Date(1647405871460)
Wed Mar 16 2022 12:44:31 GMT+0800 (中国标准时间)
now.toLocaleString  //注意,调用是一个方法,而不是一个属性
ƒ toLocaleString() { [native code] }
now.toLocaleString()
'2022/3/16 12:44:31'
now.toGMTString()
'Wed, 16 Mar 2022 04:44:31 GMT'
```



## 5.2、JSON

> json是什么

早期,所有数据传输习惯使用xml文件

+ [JSON](https://baike.baidu.com/item/JSON)([JavaScript](https://baike.baidu.com/item/JavaScript) Object Notation, JS 对象简谱) 是一种轻量级的数据交换格式
+ 简洁和清晰的层次结构使得 JSON 成为理想的数据交换语言
+ 易于人阅读和编写，同时也易于机器解析和生成，并有效地提升网络传输效率



在JavaScript一切皆为对象、任何JavaScript支持的类型都可以用JSON来表示; number,string...

> 格式:

+ 对象都用{}
+ 数组都用[]
+ 所有的键值对都是用 key:value



JSON字符串和JavaScript对象的转化

```JavaScript
let user ={
    name:"qinjiang",
    age:'3',
    sex:'female'
}
console.log(user)

//对象转化为JSON字符串   {"name":"qinjiang","age":"3","sex":"female"}
let jsonuser = JSON.stringify(user)
console.log(jsonuser)

//json 字符串转换为对象,参数为JSON字符串  Object
let obj = JSON.parse('{"name":"qinjiang","age":"3","sex":"female"}')
console.log(obj)
```



很多人搞不清楚,JSON和JavaScript对象的区别,区别如下

![image-20220316135859644](typora%E4%BF%9D%E5%AD%98%E7%9A%84%E5%9B%BE%E7%89%87/image-20220316135859644.png)







## 6、面向对象编程

### 6.1、什么是面向对象

JavaScript、Java、c#....  面向对象;  JavaScript有一些区别!

类: 一个模板

对象: 一个具体的事例

在JavaScript这个需要大家换一下思维方式!

> 原型:

![image-20220316141423305](typora%E4%BF%9D%E5%AD%98%E7%9A%84%E5%9B%BE%E7%89%87/image-20220316141423305.png)













































































