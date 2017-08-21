# JavaScript概述

## 一、什么是JavaScript?

1. JavaScript主要用于HTML的页面，嵌入在HTML的源码中。
2. JavaScript是因特网上最流行的脚本语言，它存在于全世界所有 Web 浏览器中，能够增强用户与 Web 站点和 Web 应用程序之间的交互。
3. JS是弱类型语言,没有类型声明,它的变量不必具有一个明确的类型。
4. JS是脚本语言，换句话说，可以用来编程的并且直接执行源代码的语言,就是脚本语言。
5. JS也是解释性的语言。何为解释性语言?是在运行的时候将程序直接翻译成机器的语言
6. JavaScript是一种基于对象\(Object\)和事件驱动\(Event Driven\)并具有安全性能的脚本语言,可广泛用于服务器、PC、笔记本电脑、平板电脑和智能手机等设备。
7. HTML5的出现更是突出了JavaScript的重要性，例如HTML5的绘图支持、本地存储、离线应用、客户端通信等，都大量使用了JavaScript。

## 二、JavaScript发展史

1. 1990年底，欧洲核能研究组织（CERN）科学家Tim Berners-Lee（蒂姆 伯纳斯-李），互联网之父
2. 1992年底，美国国家超级电脑应用中心（NCSA）开始开发一个独立的浏览器，叫做Mosaic （马赛克） 。
3. 1994年10月，NCSA的一个主要程序员MarcAndreessen（马克 爱德森）联合风险投资家Jim Clark（ 吉姆·克拉克），成立了Mosaic通信公司（Mosaic Communications），不久后改名为网景Netscape。这家公司的方向，就是在Mosaic的基础上，开发面向普通用户的新一代的浏览器 Netscape Navigator。
4. 1994年12月，Navigator发布了1.0版，市场份额一举超过90%。
5. 1995年，Netscape公司Brendan Eich开发这种网页脚本语言。1995年5月，Brendan Eich只用了10天，就设计完成了这种语言的第一版liveScript。
6. 1995年12月4日，Netscape公司与Sun公司联合发布了JavaScript语言。
7. 1996年3月，Navigator 2.0浏览器正式内置了JavaScript脚本语言。
8. 1996年8月，微软模仿JavaScript开发了一种相近的语言，取名为JScript（JavaScript是Netscape的注册商标，微软不能用），首先内置于IE 3.0。Netscape公司面临丧失浏览器脚本语言的主导权的局面。
9. 1997年 IE4与nn4平分天下。网景公司将javaScript交给ECMA\(European Computer Manufacturers Association\)组织，以此来抵制微软的垄断。
10. 1998年 ECMAScript 2.0
11. 1999年 ECMAScript 3.0
12. 2008年 ECMAScript4.0应为升级太大，废弃
13. 2009年 ECMASript5.0发布
14. 2011年ECMAscript 5.1版发布，并且成为ISO国际标准（ISO/IEC 16262:2011）。到了2012年底，所有主要浏览器都支持ECMAScript 5.1版的全部功能。
15. 2015年 ECMAScript6.0 改名为 ECMAScript2015

## 三、语法组成

1. 基本语法：借鉴C语言和Java语言。
2. 数据结构：借鉴Java语言，包括将值分成原始值和对象两大类。
3. 函数的用法：借鉴Scheme语言和Awk语言，将函数当作第一等公民，并引入闭包。
4. 原型继承模型：借鉴Self语言（Smalltalk的一种变种）。
5. 正则表达式：借鉴Perl语言。
6. 字符串和数组处理：借鉴Python语言。

## 四、JavaScript主要特点

1. **简单性**

   ```
   它是基于Java基本语句和控制流之上的简单而紧凑的设计，但是相比Java来说，它的变量类型是采用弱类型，未采用严格的数据类型。
   ```

2. **安全性：**

   ```
   JS不允许访问本地硬盘，不能将数据存入到服务器上，不允许对网络文档进行修改和删除，
   只能通过浏览器实现信息浏览或动态交互，从而有效的防止数据的丢失。
   ```

3. 动态性

   ```
   JS可以直接对用户或客户输入做出响应，无须经过Web程序。
   它对用户的响应采用以事件驱动的方式进行，即由某种操作动作引起相应的事件响应，如：点击鼠标、移动窗口、选择菜单等。
   ```

1. **跨平台性**

   ```
   JS依赖于浏览器本身，与操作环境无关。只要能运行浏览器的计算机，
   并安装了支持JS的浏览器就可以正确执行，从而实现了“编写一次，走遍天下”的梦想。
   ```

## 五、JavaScript组成部分

1. **ECMAScript** 他是JavaScript的核心，描述了该语言的语法和基本对象。
2. **BOM\(browerobject model 浏览器对象模型\)。** 描述了与浏览器进行交互的方法和接口。BOM提供了独立于内容而与浏览器窗口进行交互的对象，例如可以移动，调整浏览器大小的window对象，可以用于导航的location对象与history对象，可以获取浏览器，操作系统与用户屏幕信息的navigator与screen对象，可以使用document作为访问HTML文档的入口，管理框架的frames对象等。
3. **DOM\(document object model 文档对象模型\)。** 通过 DOM，可以访问所有的 HTML 元素，连同它们所包含的文本和属性，可以对其中的内容进行修改和删除，同时也可以创建新的元素。

## 六、常用的开发工具

1. **Sublime**

2. HBuilder  ide  集成开发环境  免费 不难用

3. **WebStrom**   用的最多  idea基础  收费

   ​



