# 变量和数据类型

## 一、什么是变量

​    变量的主要作用是存取数据、提供存放信息的容器。对于变量必须明确变量的命名、变量的类型、变量的声明及其变量的作用域

## 二、变量的命名

### 1、命名法

1. 匈牙利命名法

   ```
   类型+对象描述
   ```

2. 驼峰命名法

   ```
   1. 全部小写 
       单词之间用_下划线分割

   2. 大小写混合
     2.1 大驼峰
           每个单词首字母大写
     2.2 小驼峰
           第一个字母首字母小写.其他字母大写
   ```

### 2、规则

1. 第一个字符必须是英文字母，或者是下划线\(\_\)；其后的字符，可以是英文字母，数字，下划线；
2. 变量名不能是JavaScript的保留字,关键字 
3. 前缀应当是名词。\(函数的名字前缀为动词，以此区分变量和函数\)

### 3、注意事项

​    在对变量命名时，最好把变量的意义与其代表的意思对应起来，以免出现错误

## 三、变量声明

### 1、声明

```
变量必须要先声明才能使用，使用var声明变量 
变量以可以不作声明，而在使用时再根据数据的类型来确其变量的类型
```

### 2、注意事项

1. 没有类型
2. 重复声明
3. 隐身声明
4. 不声明直接赋值

### 3、正确声明方式

先声明,后读写  
先赋值,后运算

## 四、变量类型

### 1、值类型\(简单数据类型\)

1. 占用空间固定,保存在栈中
2. 保存在复制的是值本身
3. 使用 typeof 检测数据类型
4. 基本类型数据都是值类型

### 2、引用类型\(复杂数据类型\)

1. 占用空间不固定.保存在堆里面
2. 保存于复制的是指向对象的一个指针
3. 使用 instanceof检测数据类型
4. 使用new\(\)方法构造出来的对象是引用类型

## 五、简单数据类型

### 1、说明

​    简单数据类型共分5种：**Number、Boolean、String、Null、Undefined** \(ECMAScript6新增：Symbol\)

| 数据类型 | 数据值 | 说明 |
| :---: | :--- | :--- |
| Undefined | undefined | 当声明一个变量但是并没有赋值时，变量的类型是Undefine类型 |
| Null | null | 对象指针为空 |
| Boolean | true   false | true\false两个值都必须小写 |
| Number | 10    3.14  3.  .5 整数与浮点数 | NaN   ---- not a number本应该返回数值型数据的函数，如果返回的值不是数值型测返回NaN  isNaN\(\)---不是数字返回true   是数字返回false |
| String | “Hello”     ‘Hello’   “a”   ’a’ | 后续学习 |
| Object | 对象 | 后续学习 |

### 2、Number\(重点\)

#### 2.1、说明

​    数值类型共分4种值：**整数、浮点数、无穷大、NaN**。对数值来说，最常见的数值字面量是10进制。比如：20, 30, 5.5 这些值都是用10进制表示的。

#### 2.2、整形

1. 说明

   ```
   没有小数点的。除了我们常见的可以使用8进制和16进制的整数来表示。8进制的范围是(0-7)， 16进制的范围是(0-F)
   ```

2. 示例代码

   ```
   var num = 25;  // 10进制的25
   alert(num); //弹出：25
   var num1 = 025; // 8进制用0开始。表示一个8进制的25。
   alert(num1);   // 弹出：21    注意：弹出显示的时候，总是用10进制的形式。
   var num2 = 0x25; // 0x开始表示这个数是16进制。这是个16进制中的25。 注意：这里的x可以大写X也可以小写x
   alert(num2);    //弹出：37
   var num3 = 0XAF;
   alert(num3);  //弹出：175

   注意：如果8进制数字超出了进制范围(比如出现8、9)，则自动忽略前导0，把这个数字作为十进制的数字类处理。例如：
   var num4 = 089;
   alert(num4);  //弹出：89。 并不会出现错误
   ```

#### 2.3、浮点型

1. 说明

   ```
   所谓浮点数值，就是该数值中必须包含一个小数点，并且小数点后面必须至少有一位数字。
   浮点数直接量一般有两种写法：直接带小数点的和使用科学计数法。
   ```

2. 示例代码

   ```
   var f1 = 3.14;   // 带小数点的直接量写法
   var f2 = 3.158899e5; //科学计数法：  表示 3.158899 * 10^5
   ```

#### 2.4、无穷大\(Infinity\)

1. 说明

   ```
   ECMAScript并不能储存所有的数，所以能表示的数有个范围。所能表示的数最大值和最小值都保存在Number这个内置对象中
   ```

2. 示例代码

   ```
   //如果数值超出了最大值和最小值，则用Infinity和-Infinity表示。
   alert(Number.MAX_VALUE);
   alert(Number.MIN_VALUE);
   //弹出：Infinityalert(-1.1 / 0);    //弹出：-Infinity
   alert(1.1 / 0);
   ```

#### 2.5、NaN\( not a number 不是个数\):

1. 说明

   ```
   表示不是一个数字，当0/0 的时候不是无穷大，而是NaN。或者把一个非数字形式的字符串转换成数字时都会返回NaN
   ```

2. 示例代码

   ```
   alert(0 / 0);  //弹出：NaN
   alert(parseInt("60"));    //弹出：60    说明：parseInt("");可以把字符串形式的数字转换成Number
   alert(parseInt("a"));    //弹出：NaN

   //注意：NaN是个非常特别的东东。因为即使他自己和自己都不相等。
   var v = 0 / 0;
   alert(v == v);  //弹出false
   alert(v != v);    //弹出true。  所以：可以通过这种方式来判断这个数是否为NaN

   /*
     另外：isNaN()函数如果 x 是特殊的非数字值 NaN（或者能被转换为这样的值），返回的值就是 true。如果 x 是其他值,
     则 返回 false。
   */
   alert(isNaN(3));//返回false
   alert(isNaN("3"));   //返回false
   alert(isNaN("blue"));//返回true
   alert(isNaN(true));//返回false . true可以转换成数字1
   alert(isNaN(null));//返回false    null可以转换为数字0
   alert(isNaN(undefined));//返回true
   ```

### 3、Boolean类型\(重点\)

​    只有两个值：true和false。true表示逻辑上的**对/正确**，false表示逻辑上的**错**。

### 4、String类型\(重点\)

#### 4.1、定义

​    用''或""括起来的字符表示

#### 4.2、注意事项

1. 单引号或双引号要匹配，不能一边用双引号，一边用单引号 ，左右符号要匹配。
2. JavaScript统一每个字符使用Unitcode码来进行编码，每个字符占16位\(2个字节\)。
3. 在其他语言中多用单引号表示一个字符，双引号表示字节。但是对JavaScript来说，不存在字符类型的数据。
4. '本身也是一个字符，那就可以用""括起来，比如"I'm OK"包含的字符是I，'，m，空格，O，K这6个字符。如果字符串内部既包含'又包含"怎么办？可以用转义字符\来标识

#### 4.3、转意字符

​    有些字符不可见或有特殊意义，比如换行符，制表符, 双引号等，

| 代码 | 输出 |
| :---: | :---: |
| **\'** | **单引号** |
| **\"** | **双引号** |
| \& | 和号 |
| \ | 反斜杠 |
| **\n** | **换行符** |
| \r | 回车符 |
| **\t** | **制表符** |
| \b | 退格符 |
| \f | 换页符 |

### 5、Undefined

​    Undefined 类型只有一个值，即特殊的 undefined 。在使用 var 声明变量但未对其加以初始化时，  
这个变量的值就是 undefined

### 6、Null

​    表示一个空对象指针,值 undefined 实际上是从值 null 派生来的，因此 ECMAScript 把它们定义为相等的

**注**:尽管这两个值相等，但它们的含义不同,undefined 是声明了变量但未对其初始化时赋予该变量的值，null 则用于表示尚未存在的对象。如果函数或方法要返回的是对象，那么找不到该对象时，返回的通常是null

## 六、数据类型转换

### 1、自动类型转换

1. 定义

   ```
   在解释执行的过程中，会根据需要进行相应的自动类型转换
   ```

2. 其它类型转换成布尔类型

   ```
   undefined —> false
   null —> false
   数值       0,0.0,NaN —> false   其他数值—> true
   字符串    ""—>false    "etef" —> true
   其他对象—> true
   总结：存在的东东，转换成true， 不存在的东东转换成flase
   ```

3. 其它类型转换成数值类型

   ```
   undefined —> NaN
   null —> 0
   字符串——>数值—>     "34234"—>34234,  "324sdfs3423" —> NaN,  "" —> 0
   布尔类型——>数值    true->1   false->0
   总结：能转成数字的就转成对应的数字。不能转成数字的要么0或1要么NaN
   ```

4. 其它类型转换成字符串类型

   ```
   undefined —>"undefined"
   null —>"null"
   布尔类型     true —>”true”     false —>"false"
   数值类型转成字符串    12321 —>"12321"   NaN —>"NaN"
   总结：字面值是什么就转成什么
   ```

### 2、强制类型转换

1. 其他类型转成成字符串

   ```
   var a = 10;
   alert(a + "");  // 直接和一个长度为0的空字符链接
   alert(a.toString()); //调用这个变量的toString()方法
   alert(String(a));  //使用String转型函数
   ```

2. 字符串转数字

   ```
   var s = "123";
   alert(parseInt(s));
   alert(parseFloat(s));

   注意：使用parseXxx转换
   1、转换为数字的时候，会忽略前面的空格
   2、如果是数组开头然后是字母，则会只转前面的数字
   3、如果是是字母开头则返回NaN
   4、在使用parseInt的时候，可以传入第二个参数，表示这个数的进制，然后就转换成对应的10进制数返回。
   alert(parseInt("  12"));  //忽略前面的空白字符
   alert(ParseInt("12ab3");  //弹出：12.  从字母后面的统统忽略掉
   alert(parseInt("a123"));  // 弹出：NaN
   ```

   ​



