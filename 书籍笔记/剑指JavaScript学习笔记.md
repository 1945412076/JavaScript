##  一、JavaScript的特性

### 1.1 JavaScript的四大特性

动态型的、弱类型的、解释型的、面向对象的脚步语言

1. 动态型的：编译是变量没有具体类型，只有在运行时才能确定变量类型
2. 弱类型的：定义变量时不能定义具体类型，
3. 解释型的：JavaScript在运行中逐行进行解释，不用编译成机械码
4. 面向对象的：懂得都懂。

### 1.2 严格模式

在文件或函数第一行添加

```"use strict"```



## 二、变量

三大声明方法：var、let、const（let、const是ES6模版推出来的）

### 2.1 var声明

#### 2.2.1 var作用域

1. 函数作用域：在整个函数中国可以使用var声明的变量

2. 全局作用域：在```<script></Script>```标签中声明，var声明的变量有效范围就是整标签

   > 注意：var声明全局作用域，该变量会成为window的属性



#### 2.2.2  var声明提升

无论是在全局作用域或在函数作用域声明，var声明的变量多厚提升到该作用最前面。



### 2.2 let声明

#### 2.2.1  let块作用域

```js
//var声明的变量
if(true){
  var id=1;
  console.log(id); //1
}
	console.log(id);//1

//let声明的变量
if(true){
  let id = 1;
  console.log(id); //1
}
  console.log(id); //ReferenceError:id is not defined
```

>注意：如果控制台：ReferenceError:id is not defined，表示一个不存在的变量被引用



#### 2.2.2 暂时性死区

ES6明确规定：如果区块中存在let命令，那么这个区块对这些命令声明的变量从一开始就形成了封闭作用域

>简单说，let变量声明不会预处理，不会代码提升





### 2.3 const声明

const也是块作用域，let用来声明变量，const声明的是不可变得

![image-20230509222203746](/Users/kaiqiang/Library/Application Support/typora-user-images/image-20230509222203746.png)

## 三、基本数据类型

七大数据类型：Number、String、Boolean、Undefined、Null、Symbol（ES2015新增）、BigInt（ES2020新增）

### 3.1使用typeof检测数据类型

mconsole.log(typeof 666)



### 3.2 Number类型

#### 3.2.1 Number认识

javascript中没有integer和float等类型，javaScript的任何数字都是Number

#### 3.2.2 Infinity和-Infinity类型

1. Infinity:无穷大
2. -Infinity:无穷小

#### 3.2.3 特殊数值 NaN

1. NaN本意：不是一个数 类似：'333nan'
2. NaN本身是Number类型
3. NaN并不自等



### 3.3 String类型

#### 3.3.1 认识String

String就是字符串可以调用length

#### 3.3.2  模板字符串

ES6引入的新属性——模板字符串。

1. 模板字符串是增强版的字符串，用反引号(`)标识。
2. 模板字符串可以当作普通字符串使用，也可以用来定义多行字符串，或者在字符串中嵌入变量
3. 在模板字符串嵌入变量时，需要将变量名写在'${....}'之中，在执行时会立即在线解析求值



### 3.4 Boolean类型

Boolean就两个值：true和false



### 3.5 Undefined类型

说明变量声明但是没有赋值



### 3.6 Null类型

Null就是表示为'空，无效'，使用typeof检测就是object



### 3.7 BigInt类型

BigInt解决数值大于2*1024(这是平方) 使用typeof检测BigInt类型的值会返回bigint，ES2020引入的

BigInt类型的数值后面必须加n，类似(123n)



### 3.8 symbol类型

每个从 `Symbol()` 返回的 symbol 值都是唯一的。一个 symbol 值能作为对象属性的标识符；这是该数据类型仅有的目的

