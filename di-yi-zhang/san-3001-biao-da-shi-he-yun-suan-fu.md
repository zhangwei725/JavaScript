# 表达式和运算符

## 一、表达式

### 1、定义

1. 表达式是产生一个结果值的式子,JavaScript的表达式,是由变量,和运算符组成
2. 表达式可以作为参数传递给函数,或将表达式的结果赋予变量保存起来


1. 表达式的结果值有多种类型,比如布尔型,字符串类,或者数值型等,因此常有逻辑表达式,数值表达式和布尔表达式之说.

### 2、分类

1. 原始表达式
2. 对象和数组的初始化表达式
3. 属性访问表达式
4. 调用表达式
5. 对象创建表达式

## 二、运算符

### 1、定义

​	运算符也叫操作符。作用是去操作数据值，然后进行各种计算。**ECMAScript 操作符的与众不同之处在于，它们能够适用于很多值，例如字符串、数字值、布尔值，甚至对象

### 2、算术运算符

> +、-、*、/、%。
>
> 这几个运算符都需要两个数据参与运算。

1. **+ **运算**符：运算规则**

- 如果两个都是Number则，则就按照普通的数学加法运算。


- 如果有一个是字符串，就按照字符串的串联的方式连接。(如果另外一个不是字符串，则先转换成字符串再连)。
- 如果有一个是NaN，则结果就是NaN。
- 如果同时是Infinity或-Infinity，则结果就是Infinity或-Infinity。
- 如果一个是Infinity另外一个是-Infinity，则结果为NaN。

1. **- 运算符：运算符规则**

- 如果两个都是Number则，则就按照普通的数学减法运算。
- 如果有一个操作数是字符串、布尔值、null 或undefined，则先在后台调用Number()转型函数将其转换为数值，然后再根据正常减法计算。如果转换的结果有一个是NaN,则减法的结果就是NaN
- 如果有一个操作数是对象，则调用对象的valueOf()方法以取得表示该对象的数值。如果得到的值是NaN，则减法的结果就是NaN。如果对象没有valueOf()方法，则调用其toString()方法并将得到的字符串转换为数值**(了解)**

1. **\* 运算符：运算符规则。**

- 运算规则同减法。

1. **/ 运算符：运算规则**

- 就是普通的除法运算，运算规则同 \*

1. **%运算符：运算规则**

- 求余(求模)运算。

```javascript
var v = 10 % 2;   // 余0
alert(10 % 3); // 结果 ： 1
alert(-10 % 3); // 结果： -1   说明：求余的时候，符号与被除数保持一致。
alert(10 % -3); // 结果： 1
alert(1 % 0.3);  // 结果：0.1
```



### 3、一元运算符

1. ++自增操作: 对要操作的变量进行+1的操作，并把+1之后的结果重写赋值给这个变量。可以在变量前也可以在变量后。任何变量都可以使用，但是对非Number类型的变量操作的时候，需要先按照前面的规则转换成Number然后再自增**1.**

```javascript
var a = 10;
var b = a++;  //把a的值自增1，a的值变为11.  注意：a++表达式的值，仍然是a自增之前的值，所以b的值是是10

var c = 10;
var d = ++a;  //把a的值自增1，a的值变为11.  注意：++a表达式的值，是a自增之后的值，所以d的值是11

var m = "123";
m++;  //先把m使new Number(m)之后再转换进行自增的操作。
```

1. --自减操作: 对要操作的变量进行减1的操作，并把-1之后的结果重新赋值给这个变量。  计算方法同++。

```javascript
var a = 10;
var b = a--;  //把a的值自减1，a的值变为9.  注意：a--表达式的值，仍然是a自减之前的值，所以b的值是是10

var c = 10;
var d = --a;  //把a的值自减1，a的值变为9.  注意：--a表达式的值，是a自减之后的值，所以d的值是9

var m = "123";
m--;  //先把m使用转型函数Number(m)之后再转换进行自减的操作。
```

### 4、赋值运算符和复合赋值运算符

> =、+=、-=、*=、/=、%=
>
> **使用赋值操作符的注意目的是简化表达式的书写，并不会带来任何的性能的提示。**

```javascript
var n = 10;
n += 4;  //等价于 n = n + 4;  运算结束后n的值为14

var m = "6";
m -= 5;   // 会先把m转换成数字之后(m = new Number(m))，再执行  m = m - 5;
```

### 5、比较运算符

> \>、>=、<、<=、\==、\===、 !=、!\==
>
> 比较运算符是对运算符的坐标和右边的两个数据进行比较。

- 如果两个都是数字，就是普通的数字比较。
- 如果有一个是数字，就把另外一个不是数字的使用Number(var)的方式转换为数字再比较
- 如果两个都是字符串，则比较的是字符串中的字符在字母表中的顺序。(或者说比较是他们的编码值)
- 如果有一个是NaN，则结果一定是false。==但是有一种情况，如果比较特殊NaN  !=  NaN则是true。==

> ==**\== 和 != 是判断两个操作数是否相等。规则：**==

- 如果两个都是简单类型中的Number类型，直接判断数值是否相等。

```javascrept
alert(10 == 10.0);  //  true
```

- 如果有一个NaN参与比较，则总是不等的。
- null和undefined之间是相等
- 如果有一个操作数是布尔值，则在比较相等性之前先将其转换为数值—— false 转换为 0，而
  true 转换为 1；
- 如果一个字符串与数值比较，则把字符串转换成数值之后再比较
- 如果一个对象和一个基本类型比较，则调用对象的valueOf方法，转变成基本类型之后再比较(暂时先了解)
- 如果个 2 对象比较，则比较两个对象是否为同一个对象。是就相同，不是就不同。(暂时先了解)

```javascript
alert(NaN == false);  // fasle
alert(NaN == true);  // false
alert(NaN == 1); //false；
alert(NaN == NaN); // fasle
alert(NaN != NaN); // true

alert(null == null); // true
alert(null == undefined); // true
alert(undefined == undefined); // true

alert("1" == 1); //true
alert("1a" == 1);  //false  “1a"会被转换为NaN

alert(1 == true); //true  会把true转成1之后再比较
alert(0 == null);  //false  null与任何的非null的都不相等
```

> ==**\=\==   !\== 全等判断**==
>
> 全等在转换前不做任何的转换，如果两个一样就相等，否则就不等。

```javascript
alert("1" === 1);  //false 一个string类型，一个number类型，所以不等
alert(null === undefined);  // false
alert("abc" === "abc");  // true
```



### 6、逻辑运算符

> 只有三种逻辑运算符：&&、||、! 。而且 && 和|| 都是短路的形式。 **注意：不像其他语言有非短路的&、|,也没有^(异或)**

1. **逻辑非  ！** 。注意：这个是运算符只需要一个数据参与运算。**不管参与运算的 是什么数据，最终结果一定是Boolean值**.逻辑非的运算逻辑是，不管什么类型，先转换成Boolean值，再取反得到最终的结果。 取反的意思就是true变false，false变true

```javascript
alert(!Null);  //true。  因为null会转为fasle，所以取反之后变为true
alert(!0);  // true
```

1. **逻辑与 &&  。**  **只要有一个是false，则返回false。**(只有两个都是true的情况下才返回true)。 ==逻辑与&&的结果不一定是Boolean值 以下为特殊情况：==

- 有短路的特点：如果 **第一个** 是false或者可以转换成false，则 **结果就是第一个** 。
- 如果 **第一个** 是true或者可以转换成true，则 **结果就是第二个** 。

```javascript
var a = 10;
alert(false && a++); //第一个操作数是false，所以最终结果是false。由于短路的关系，所以不会再去计算第二个表达式。
alert(a); //  结果：10

var b = 20;
alert(null && b++);  // 第一个操作数是null，结果为null，且不会再去判断第二个。
alert(b);  // 结果：20

var c = 30;
alert(new Number(5) && c++);  //结果 30.第一个操作数是对象，所以直接返回第二个操作数。
alert(c); //结果：31
```

1. **逻辑或 || 。** ==只要有一个是true，结果就是true。==  与逻辑与一样，结果也不一定是Boolean值。特殊情况如下：

- 也有短路的特点：如果 **第一个** 是true或者能转换成true，则直接返回第一个,不再去判断第二个
- 如果 **第一个** 是false或可以转换成false，则直接返回第二个。

```javascript
var a = 10;
alert(true || a++);  // 结果true，且不会计算第二个表达式

var b = 20;
alert(new Number(5) || b++); //结果为第一个(5)，且不会计算第二个。

var c = 30;
alert(null || c++); //结果为30
```

> ***&&()和|| 的结果总结：***
>
> 1. 如果第一个可以决定结果，则最终结果就是第一个表达式的值
> 2. 如果第一个不能决定结果，则最终结果就是第二个表达式的值

### 7、 三元运算符(条件运算符)

> 三元运算符的意思是指，需要三个操作数参与运算。
>
> 语法：`逻辑值(表达式) ?  表达式1 :  表达式2`
>
> 结果：如果逻辑值是true，则最终返回表达式1的值，如果逻辑值是false，则最终结果返回表达式2的值。
>
> ==注意：如果逻辑值不是Boolean值，则先按照转型函数Boolean()的方式转变成Boolean，再进行计算== 

```javascript
var a = 0 ? 1 : 2;  //结果是2
var b = null ? 1 : 2; //结果是2
var c = "a" ? 1 : 2; //结果是1
```

### 8、typeof操作符

> typeof   操作符用来检测给定的变量的类型。
>
> 语法：  typeof  变量;
>
> *注意：typeof是一个操作符，而不是方法，所以typeof后面的操作数完全不需要添加括号。*

```javascript
var a = "abc";
alert(typeof a);  //弹出：string  注意：s是小写
```

> typeof操作符的计算结果只有一下6种：

1. "undefined" ——如果这个值未声明，或者声明了但没有赋值
2. "boolean" ——如果这个值是布尔值；
3. "string" ——如果这个值是字符串；
4. "number" ——如果这个值是数值；
5. "object" ——如果这个值是对象或 null ；
6. "function" ——如果这个值是函数。

```javascript
var a;
alert(typeof a);  // undefined
alert(typeof b);  // undefined
alert(null);  //object
alert("abc"); //string
alert(new Object()); //object
alert(new String()); // object
```

### 9、逗号运算符

> - 使用逗号操作符可以在一条语句中执行多个操作。
> - 逗号操作符还可以用于赋值。在用于赋值时，逗号操作符总会返回表达式中的最后一项

```javascript
//var a, b, c, d;   //使用逗号操作符同时声明了4个变量。
var a = (1, 2, 3, 4);   // a= 4.  逗号操作符返回最后一个值。
alert(a);  //弹出： 4
```

## 
