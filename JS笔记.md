# JavaScript初识

### JS的作用

+ 表单动态校验（密码强度检测）
+ 网页特效
+ 服务端开发
+ 桌面程序
+ APP
+ 控制硬件
+ 游戏开发

### 浏览器怎么执行JS

+ 渲染引擎：用于解析HTML和CSS，俗称内核
+ JS引擎：也称为JS解释器。用于读取网页中的JS代码，对其处理后运行。

浏览器本身并不会执行JS代码，而是通过内置的JS引擎来执行JS代码，JS引擎执行代码时逐行解释每一句源码，然后由计算机去执行，所以JS语言归为脚本语言，会逐行解释执行。

### JS组成

+ JS语法
+ 页面文档对象模型
+ 浏览器对象模型

### JS的三种书写方式

+ 行内
+ 内嵌----> 像CSS一样写一个script在head位置
+ 外部---->在双标签前面写src="......" 而且双标签之间千万千万不能写代码

HTML中推荐使用双引号，JS中推荐使用单引号

# JS注释

同c语言

# JS输入输出语句

+ alert(msg)	浏览器弹出警示框
+ console.log(msg)    浏览器控制台打印输出信息---->程序员测试用
+ prompt(info)    浏览器弹出输入框，用户可以输入--->取到的值是字符串
+ console.dir（msg）可以打印我们返回的元素对象 更好的查看里面的属性和方法

# 变量

### 变量的使用

声明变量--var 变量名;

赋值--变量名=值;

# 数据类型

JS时一种弱类型或者说动态的语言，这意味着不用提前声明变量的类型，在程序运行的过程中，类型会被自动锁定（拜托，超级爽的好嘛 var 可以赋所有东西）

### 数据类型的分类

+ 简单数据类型
  + 数字 包括整数和小数 还可以写不同进制的 
    + 如八进制 var num= 010；这样 
    + 十六进制要写一个 0x在前面
    + Infinity表示无穷大 前面加一个负号表示无穷小
    + isNaN()用于判断是不是非数字 是返回false
  + 布尔值
  + 字符串 任意文本
    + 转义符同c
    + 字符串拼接 用+就可以  变量不要写到字符串中 是通过和字符串相连的方式实现的
  + 还有undefined（未声明）和Null（空）
+ typeof 后面接变量 可检测变量类型
+ 复杂数据类型：通过new关键字创建的对象如Object、Array、Date这些都属于复杂数据类型。

### 数据类型的转换

+ 转为字符串型
  + .toString()
  + String(变量)
+ ==转为数字型==
  + parseInt(变量)---->转为整形（会去掉字母）
  + parseFloat(变量)--->转为浮点
  + Number(变量)---->强制转换为数字
+ 转为布尔值型
  + Boolean(变量)
    + 会将空、否定的值都转化为false
    + 其余的值会转化为true

# JS基础

+ 断点设置 在浏览器中f12 点sources再点左边那里可以设置断点

### 数组

##### 创建数组

样式为

+ var 变量=new Array()；------>以创建一个新的数组
+ var 变量=[...,...,...];

##### 数组的长度

使用“数组名.length”可以访问数组元素的数量（数组长度）

##### 数组中新增元素

可以通过修改length长度以及索引号增加数组元素

+ 修改length长度：比如变量.length=数字 ；这样就可以改数组的长度为 某个数字了
+ 索引号增加数组元素：例如本来长度是5 你在[]里写6 就会扩容啦

### 正则表达式

##### 正则表达式概述

正则表达式是用于匹配字符串中字符组合的模式。在JavaScript中，正则表达式也是对象。

##### 正则表达式的特点

1.灵活性、逻辑性和功能性非常的强。

2.可以迅速地用极为简单的方式达到字符串的复杂控制

3.对于刚接触的人来说，比较晦涩难懂。

4.实际开发中，一般都是直接复制写好的正则表达式，但是要求会使用正则表达式并且根据实际情况修改正则表达式。

##### 创建正则表达式

+ var name=new RegExp(/表达式/);
+ var name=/表达式/;

##### 测试正则表达式

regexObj.test(str)

1.regexObj是写的正则表达式

2.str是我们要测试的文本

3.就是检测str文本是否符合我们写的正则表达式规范

##### 正则表达式的组成

一个正则表达式可以由简单的字符构成，也可以是简单和特殊字符的组合，其中特殊字符也被称为元字符，在正则表达式中是具有特殊意义的专用符号。

特殊字符可以参考：MDN

+ 边界符：
  + ^   表示匹配行首的文本（以谁开始）
  + $   表示匹配行尾的文本（以谁结束）
  + []   表示有一系列字符可供选择，只要匹配其中一个就可以了。
  + [-]表示方括号内部的范围
  + [^]表示取反
  + |表示或者
+ 量词符：
  + *重复零次或更多次
  + +重复一次或更多次
  + ？重复一次或零次
  + {n}重复n次
  + {n，}重复n次或更多次
  + {n，m}重复n到m次
+ 括号总结
  + 大括号 量词符 表示重复次数
  + 中括号 字符集合。匹配方括号中的任意字符
  + 小括号 表示优先级

+ 预定义类
  + \d  匹配0~9之间任一数字
  + \D  匹配0~9外任意字符
  + \w  匹配任意的字母、数字和下划线
  + \W  匹配除所有字母数字、下划线以外的字符
  + \s   匹配空格（包括换行符、制表符、空格符等）
  + \S  匹配非空格的字符

# 函数

### 函数的使用

样式：function  函数名（）{ 函数体 }；

或

==样式：var 函数名 = function（）{}；==

调用直接输：函数名（）即可

### 函数的返回

如果函数没有返回值就会返回undefined。

### arguments使用

arguments是伪数组

+ 不是真正意义上的数组
+ 具有length的属性---->argiments.length
+  只有函数才有
+ 它没有真正数组的一些方法 

# JS作用域

就是代码名字在某个范围起作用和效果

函数内没有赋值的变量也是全局变量

# 预解析

var 变量=值 

定义和赋值会分开 定义会放在最前面

且函数定义也会放在前面

# 对象

调用对象：

+ 输入变量的地方输入 对象名.属性名（.理解为”的“）
+ 在对象名后面加   ['属性名']

### 什么是对象

对象是由属性和方法组成的

+ 属性：事物的特征，在对象中用属性来表示（常用名词）
+ 方法：事物的行为，在对象中用方法来表示（常用动词）

### 为什么需要对象

保存一个值时，可以使用变量，保存多个值时，可以使用数组。

但JS中的对象表达结构更清晰，更强大。

### 创建对象的三种方式

##### 用字面量创建对象

就是花括号{}里面包含了表达这个具体事务（对象）的属性和方法

样式举例：var 对象名={ 属性1：...，方法2：...；}；

##### 用new Object创建对象

样式：var 对象名= new Object（）；

追加方法：直接在下一行写对象名.属性名=...

##### 利用构造函数创建对象

+ 构造函数创建对象的好处是一次可以创建多个对象
+ 构造函数 就是把我们对象里面一些相同的属性和方法抽象出来封装到函数里面
+ 创建构造函数样式：function 构造函数名（）{this.属性=值；}
+ 调用构造函数new 构造函数名（）；
+ 构造函数首字母要大写
+ 构造函数不需要return就可以返回结果

### 遍历对象

想要输出对象里面的多个属性

样式为：for（变量名 in 对象名）

引用变量自动往里面放所有的属性

# 内置对象

### 什么是内置对象

+ 内置对象就是JS语言自带的一些对象，这些对象供开发者使用，并提供了一些常用的或是最基本而必要的功能（属性和方法）
+ 内置对象的最大优点就是帮助我们快速开发
+ JS提供了多个内置对象：Math、Data、Array、String等
+ 想要使用可以去MDN网站查找

# Web API

### Web APIs和JS基础关联性

+ JS基础知识基本语法 做不了常用的页面交互效果
+ Web APIs是JS独有的部分 主要学习页面交互功能

### API

API是一些预先定义的函数，目的是提供应用程序与开发人员基于某软件或硬件得以访问一组例程的能力，而又无需访问源码。

### Web API

是浏览器提供的一套操作浏览器功能，主要针对浏览器提供的接口

# DOM

+ 文档对象模型
+ DOM就是把文档当作一个对象来看待
+ DOM的顶级对象是document
+ DOM主要学习的是操作页面元素
+ DOM是W3C标准规范

1.对于JS，为了能够使JS操作HTML，JS就有了一套自己的dom编程接口。

2.对于HTML，dom使得html形成一棵dom树。包括文档、元素、节点。

### 什么是DOM

文档对象模型（DOM），是一种标准编程接口。W3C已经定义了一系列的DOM接口，通过这些DOM接口可以改变网页的内容、结果、样式。

### DOM树

+ 文档：一个页面就是一个文档，DOM中使用document表示
+ 元素：页面中的所有标签都是元素，DOM中用element表示
+ 节点：网页中的所有内容都是节点（标签、属性、文本、注释等），DOM中用node表示

==DOM把以上内容都看成对象==

### 获取元素

##### 根据ID获取

+ 样式为：element.getElementById（'id'）

##### 根据标签名获取

+ 样式为：element.getElementsTagName（'元素'）

+ 得到的是对象的集合

+ 输出要在元素后面加s

##### 通过HTML5新增的方法获取

+ 考虑兼容性不可使用
+ 样式为：element.getElementsClassName（'元素'）//根据类名返回元素对象集合
+ 样式为：element.querySelector（'选择器'） //根据指定选择器返回第一个元素对象--->比如.什么什么就是类选择器
  + 只能返回第一个元素对象
  + 返回全部的话：element.querySelectorAll（'选择器'）

##### 特殊元素获取

+ 获取body标签
  + 样式element.body；
+ 获取html元素
  + 样式element.documentElement；

### 事件基础

##### 事件概述

JS使我们有能力创建动态页面，而事件是可以被JS侦测到的行为

简单理解：触发---响应机制

事件由三部分组成： 事件源 事件类型 事件处理程序

+ 事件源 事件被触发的对象 如 按钮
  + var btn=button.getElementById('btn')
+ 事件类型 如何触发 什么事件 比如鼠标点击（onclick） 还是鼠标经过 还是键盘按下
+ 事件处理程序 通过一个函数赋值的方式完成
  + btn.onclick=function( ){.....}

##### 执行事件的步骤

+ 获取事件源
+ 注册事件（绑定事件）
+ 添加事件处理程序

##### 鼠标事件操作

+ onclick鼠标点击左键触发。
+ onmouseover鼠标经过触发
+ onmouseout鼠标离开触发
+ onfocus获得鼠标焦点触发
+ onblur失去鼠标焦点触发
+ onmousemove鼠标移动触发
+ onmouseup鼠标弹起触发
+ onmousedown鼠标按下触发

### 操作元素

##### 改变元素内容

+ element.innerText=  可以改变元素内容(不识别html标签)

+ element.innerHTML=  可以改变元素内容(识别html标签)------使用最多

##### 样式属性操作

+ element.style=行内样式操作
+ element.className=类名样式操作

##### 改变元素类名

+ 在JS中想一下子改很多，而且有多个项目要更改时，可以用更改类名。
+ 正常是element.style修改的样式，但是你可以先定义一个类名是你要修改后的样式，然后写this.className='该类名'，就可以做到修改了。（会进行覆盖）
+ 如果想要保留原来的类名，可以用this.className='原来的类名 该类名'    这样。

##### 自定义属性的操作

+ 获取属性值
  + element.属性   获取属性值
  + element.getAttribute('属性')；
+ 区别：
  + element.属性 获取内置属性值（元素本身自带的属性）
  + element.getAttribute('属性')； 主要获得自定义的（标准）我们程序员自定义的属性（没错，属性是可以自定义的）
+ 设置属性值
  + element.属性=“值”  设置内置属性值。
  + element.setAttribute('属性','值')

### 节点

##### 节点概述

一般的，节点至少拥有nodeType（节点类型）、nodeName（节点名称）、nodeValue（节点值）这三个基本属性。

+ 元素节点 nodeType 为 1；
+ 属性节点 nodeType 为 2；
+ 文本节点 nodeType 为 3（文本节点包含文字、空格、换行等）；

**我们在实际开发中，节点操作的主要操作的是元素节点**

为什么要用节点操作呢？

因为在利用我们节点层次关系获取元素的时候会更简单一些。

##### 节点层级

利用DOM树可以把节点划分为不同的层级关系，常见的是父子兄层级关系

+ element.parentNode就可以直接代替var ............（得到的是离元素最近的父节点）
+ element.childNode**s**返回包含指定节点的子节点的集合，该集合为即时更新的集合。而且childNodes返回的是所有子节点 包括元素节点、文本节点等等。
+ element.children返回所有元素子节点，虽然看着很不兼容，但是各个浏览器都是允许使用的。其中对第一个元素子节点和最后一个子节点有特殊的获取方式：（包括元素节点、文本节点等等）
  + 第一个子节点：element.firstChild即为获取第一个子节点。
  + 最后的子节点：element.lastChild即为获取最后一个子节点。
  + 第一个元素子节点：element.firstElementChild即为获取第一个元素子节点。（有兼容性问题IE9+支持）
  + 最后的元素子节点：element.lastElementChild即为获取最后的元素子节点。（有兼容性问题IE9+支持）
  + 正常开发的写法都是element.children[number]这样。
+ 兄弟节点：
  + 下一个兄弟节点：element.nextSibling返回当前元素的下一个兄弟节点，找不到则返回NULL
  + 上一个兄弟节点：element.previousSibling返回当前元素上一个兄弟节点，找不到则返回null
  + 下一个元素兄弟节点：element.nextElementSibling返回当前元素的下一个元素兄弟节点（有兼容性问题IE9+支持）
  + 上一个元素兄弟节点：element.previousElementSibling返回当前元素的上一个元素兄弟节点（有兼容性问题IE9+支持）

##### 节点操作

+ 创建元素节点：var 节点名字=document.creatElement('需要创建的节点') （innerHTML也可以创建节点，但是innerHTML的原理是拼接字符串，creatElement是创建新节点，所以，creatElement会相对快很多。
+ 添加元素节点：
  + element.appendChild（child）其中element是父级，child是子级  将一个节点添加到指定父节点的子节点列表末尾，类似于CSS中的after伪元素。
  + element.insertBefore（child，指定元素）  将一个节点添加到父节点的指定子节点前面。类似于CSS里面的before伪元素。
+ 删除元素节点：element.remove(需要删除的元素节点);（例如某某元素[]）
+ 克隆元素节点：element.cloneNode(); 复制元素节点，但是复制后需要添加，相当于var name=node.cloneNode();   然后再使用添加元素节点的知识进行添加。
  + 括号为空或为false则为浅拷贝，即只复制节点本身，不copy里面的子节点。
  + 括号里为ture则为深拷贝，可以复制节点里面的所有东西。

### 事件高级

##### 注册事件

+ 注册事件概述：给元素添加事件，称为注册事件或者绑定事件。
+ 注册事件有两种方式：传统方式和方法监听注册方式。
+ 传统注册方式：
  + 利用on开头的事件onclick
  + <button onclick="alert('hi~')"></button>
  + btn.onclick=function(){}
  + 特点注册事件的唯一性
  + 同一个元素同一个事件只能设置一个处理函数，最后注册的处理函数将会覆盖前面注册的处理函数。
+ 方法监听注册方式：
  + w3c标准 推荐方法
  + addEventListener（）它是一个方法
  + IE9之前的IE不支持此方法，可使用attachEvent（）代替
  + 特点：同一个元素，同一个事件可以注册多个监听器。
  + 按注册顺序依次执行。
+ addEventListener事件监听方式
  + eventTarget.addEventListener（type，listener[，useCapture]）方法将指定的监听器注册到eventTarget（目标对象）上，当该对象触发指定的事件时，就会触发执行事件处理函数。
  + 该方法接收三个参数：
    + type：事件类型字符串，比如click，mouseover，注意这里不要带on
    + listener：事件处理函数，事件发生时，会调用该监听函数。
    + useCapture：可选参数，用于描述事件是冒泡还是捕获，是一个布尔值，默认是false。
+ attachEvent事件监听方式（IE9前版本支持）
  + eventTarget.attachEvent(eventNameWithOn,callback)方法将指定的监听器注册到eventTarget上，当该对象触发指定的事件时，指定的回调函数就会被执行。
  + 该方法接受两个函数：
    + eventNameWithOn:事件类型字符串，比如onclick，onmouseover这里要带on
    + callback：事件处理函数，当目标触发事件时回调函数被调用。

##### 解绑事件

+ 传统注册方式：eventTarget.onclick=null；

+ 方法监听注册方式：

  + eventTargrt.removeEventListener（type，listener[，useCapture]）；

    其中listener要写函数的名称，这也就意味着注册的时候也要用函数的名称。

  + eventTargrt.detachEventListener（type，listener[，useCapture]）；

    此为IE9前适用

### DOM事件流

事件流描述的是从页面中接收事件的顺序。

事件发生时会在元素节点之间按照待定的顺序传播，这个传播过程即为DOM事件流。

DOM事件流分为三个阶段：1.捕获阶段。2.当前目标阶段。3.冒泡阶段。

+ 事件冒泡：IE最早提出，事件开始时由最具体的元素接收，然后**逐级上**传到DOM最顶层节点的过程。

  有些事件是没有冒泡的：例如onblur、onfocus、onmouseenter、onmouseleave

+ 事件捕获：网景最早提出，由DOM最顶层节点开始，然后**逐级向下**传播到最具体的元素接收过程。

+ 结合useCapture，若useCapture为true则为事件捕获，false为事件冒泡

### 事件对象

div.onclick=function(event){}

1.event就是一个事件对象，写到我们侦听函数的小括号里面，当形参来看。即事件发生后，跟事件相关的一系列信息数据的集合都放到这个对象里面，这个对象就是事件对象event，他有很多的属性和方法。

2.事件对象只有有了事件才会存在，它是系统给我们自动创建的，不需要我们传递参数。

3.事件对象是我们事件的一系列相关数据的集合，跟事件相关的，比如鼠标点击里面就包含鼠标的相关信息，鼠标坐标之类的，如果是键盘事件里面就包含的键盘事件的信息，比如判断用户按下了哪个键。

4.这个事件对象我们可以自己命名 比如event、evt、e（你第一次写的空洞骑士界面音乐盒就是e）

5.事件对象也有兼容性问题 IE678通过window.event

兼容性写法e=e||window.event

##### 事件对象的常见属性和方法

+ e.target   返回触发事件的对象 标准

  e.target返回的是触发事件的对象（元素） this返回的是绑定事件的对象（元素）如绑定ul但触发的li

+ e.srcElement  返回触发事件的对象 非标准IE6~8使用

+ e.type 返回事件的类型 比如click mouseover不带on

+ e.cancelBubble 该属性阻止冒泡 非标准 IE6~8使用

+ e.stopPropagation 该方法阻止冒泡 标准

+ e.returnValue 该属性阻止默认事件 非标准IE6~8使用 比如不让链接跳转

+ e.preventDefault 该方法阻止默认事件 标准 比如不让链接跳转

##### 事件委托（代理、委派）

事件委托也称为事件代理，在jQuery里面称为事件委派。

+ 事件委托的原理：不是每个子节点单独设置事件监听器，而是事件监听器设置在其父节点上，然后利用冒泡原理影响每一个子节点（面试时用得到！！！！！！）  
+ 事件委托的作用：只操作了一次DOM，提高了程序的性能。

### 常用的鼠标事件

##### 常见的鼠标事件

+ contextmenu是鼠标右键的菜单

+ selectstart是鼠标的选中（拉动的选中）
+ click  单击鼠标左键时发生，如果右键也按下则不会发生。当用户的焦点在按钮上并按了 Enter 键时，同样会触发这个事件
+ mousedown 单击任意一个鼠标按钮时发生
+ mouseout 鼠标指针位于某个元素上且将要移出元素的边界时发生
+ mouseover  鼠标指针移出某个元素到另一个元素上时发生
+ mouseup  松开任意一个鼠标按钮时发生
+ mousemove   鼠标在某个元素上时持续发生

##### 鼠标事件对象

+ e.clientX 返回鼠标相对于浏览器窗口可视区的X坐标
+ e.clientY 返回鼠标相对于浏览器窗口可视区的Y坐标
+ e.pageX 返回鼠标相对于文档页面的X坐标 IE9+支持
+ e.pageY 返回鼠标相对于文档页面的Y坐标 IE9+支持
+ e.screenX 返回鼠标相对于电脑屏幕的X坐标
+ e.screenY 返回鼠标相对于电脑屏幕的Y坐标

##### mouseenter和mouseover的区别

mouseover经过自身盒子会触发，经过子盒子还会触发。

mouseenter只有经过自身盒子才会触发。（不会冒泡）

### 常用的键盘事件

##### 常用键盘事件

+ onkeyup 某个键盘按键被松开时触发
+ onkeydown 某个键盘按键被按下时触发
+ onkeypress 某个键盘按键被按下时触发 但是不能识别功能键 如ctrl shift 箭头等

##### 键盘事件对象

+ KeyCode 返回键盘按下键的ASCII码值
  + keyup和keydown事件不区分字母大小写，都按照大写来看
  + keypress事件区分字母大小写

# BOM

+ 浏览器对象模型
+ 把浏览器当作一个对象来看待
+ BOM的顶级对象是window
+ BOM学习的是浏览器窗口交互的一些对象
+ BOM是浏览器厂商在各自浏览器上定义的，兼容性较差 

### BOM概述

BOM（Browser Object Model）即浏览器对象模型，它提供了独立于内容而与浏览器窗口进行交互的对象，其核心对象时window。

BOM由一系列相关的对象构成，并且每个对象都提供了很多方法和属性。

BOM缺乏标准，JavaScript语法的标准化组织是ECMA，DOM的标准化组织是W3C

### BOM的构成

window对象是浏览器的顶级对象，它具有双重角色

1.它是JS访问浏览器窗口的一个接口

2.他是一个全局对象。定义在全局作用域中的变量、函数都会变成window对象的属性和方法。

在调用的时候可以省略window，前面学习的对话框都属于window对象方法，如alert、prompt等

### window对象的常见事件

##### 窗口加载事件

+ window.onload=function(){}

或者

+ window.addEventListener("load",function(){});

+ window.onload是窗口（页面）加载事件，当文档内容完全加载会触发该事件（包括图像、脚本文件、CSS文件等），就调用的处理函数。
+ document.addEventListener('DOMCotentLoaded',function(){})
  + DOMContentLoaded事件触发时，仅当DOM加载完成，不包括样式表、图片、flash等。
  + IE9以上才支持
  + 如果页面的图片很多的话，从用户访问到onload触发可能需要较长时间，交互效果就不能实现，必然影响用户体验，此时用DOMCotentLoaded事件比较合适。

注意：

+ 有了window.onload就可以把JS代码写到页面元素的上方，因为onload是等页面内容全部加载完毕，再去执行处理函数。
+ window.onload传统注册事件方式只能写一次，如果有多个，会以最后一个window.onload为准。（addEventListener则没有限制）

##### 调整窗口大小事件

+ window.onresize=function(){}
+ window.addEventListener("resize",function(){})
+ window.onresize是调整窗口大小加载事件，当触发时就调用的处理函数。
  + 只要窗口大小发生像素变化，就会触发这个事件。
  + 我们经常利用这个事件完成响应式布局。window.innerWidth为当前屏幕的宽度

### 定时器

window对象给我们提供了2个非常好用的方法-定时器

##### setTimeout()定时器

window.setTimeout(调用函数,[延迟的毫秒数]);  

setTimeout()方法用于设置一个定时器，在该定时器在定时器到期后会执行调用函数。

+ window可以省略
+ 这个调用函数可以直接写函数，或者写函数名或者采取字符串‘函数名（）’三种形式。第三种不推荐。
+ 延迟的毫秒数省略默认为0，如果写，必须是毫秒。
+ 因为定时器可能有很多，所以我们经常给定时器赋值一个标识符。

##### 停止setTimeout()定时器

window.clearTimeout（timeout ID）

+ window可以省略
+ 里面的参数就是定时器的名字

##### setlnterval()定时器

window.setInterval(调用函数,[延迟的毫秒数]);  

setlnterval()方法重复调用一个函数，每隔这个时间，就去调用一次回调函数。

+ window可以省略
+ 这个调用函数可以直接写函数，或者写函数名或者采取字符串‘函数名（）’三种形式。
+ 延迟的毫秒数省略默认为0，如果写，必须是毫秒。
+ 因为定时器可能有很多，所以我们经常给定时器赋值一个标识符。

##### 停止setInterval()定时器

window.clearInterval（interval ID）

+ window可以省略
+ 里面的参数就是定时器的名字

##### this

this的指向在函数定义的时候是确定不了的，只有函数执行的时候才能确定this到底指向谁，一般情况下this的最终指向的是那个调用它的对象

+ 全局作用域或者普通函数中this指向全局对象window、
+ 方法调用中谁调用就指向谁

### JS执行机制

##### JS是单线程

Javascript语言的一大特点就是单线程，也就是说，同一个时间只能做一件事。这是因为Javascript这门脚本语言诞生的使命所致——Javascript是为处理页面中用户的交互以及操作DOM而诞生的。

单线程就意味着，所有任务需要排队，前一个任务结束，才会执行后一个任务。这样所导致的问题是：如果JS执行的时间过长，这样就会造成页面的渲染不连贯，导致页面渲染加载阻塞的感觉。

##### 同步和异步

为了解决这个问题，利用多核CPU的计算能力，HTML5提出Web Worker标准，允许JavaScript脚本创建多个线程。于是JS出现了同步和异步。

+ 同步任务：同步任务都在主线程上执行，形成一个执行栈。
+ 异步任务：JS的异步是通过回调函数实现的。一般而言，异步事件有以下三种类型：
  + 普通事件：如click，resize
  + 资源加载：如load，error
  + 定时器：如setInterval，setTimeout

##### 执行机制

1.先执行执行栈中的同步任务

2.异步任务放入任务队列

3.一旦执行栈中的所有同步任务执行完毕，系统就会按次序读取任务队列中的异步任务，于是被读取的异步任务结束等待状态，进入执行栈，开始执行。

### location对象

##### location对象概述

window对象给我们提供了一个location属性用于获取或设置窗体的URL，并且可以解析URL。因为这个属性返回的是一个对象，所以我们将这个属性也称为location对象。

##### URL

统一资源定位符（Uniform Resource Locator，URL）是互联网上标准资源的地址。互联网上的每个文件都有唯一的一个URL，它包含的信息指出文件的位置以及浏览器应该怎么处理它。

URL的一般语法格式为：

protocol://host[:port]/path/[?query]#fragment

如http://www.itcast.cn/index.html?name=andy&age=18#link

+ protocol：通信协议 常用的http，ftp，maito
+ host：主机（域名）
+ port：端口号 可选，省略时使用方案的默认端口 如http的默认端口为80
+ path：路径 由0或多个/符号分割开的字符串，一般用来表示主机上的一个目录或文件地址
+ query：参数 以键值对的形式，通过&符号分开
+ fragment：片段 #后内容常见于锚点 链接

##### location对象的属性

+ location.href：获取或设置整个URL
+ location.host：返回主机（域名）
+ location.port：返回端口号 如果未写返回 空字符串
+ location.pathname：返回路径
+ location.search：返回参数
+ location.hash：返回片段 #后面内容

##### location对象的方法

+ location.assign()：跟href一样，可以转跳页面
+ location.replace()：替换当前页面，因为不记录历史，所以不能后退页面。
+ location.reload()：重新加载当前页面，相当于刷新按钮或者F5如果参数为true 强制刷新ctrl+f5

### navigator对象

navigator对象包含有关浏览器的信息，它有很多属性，我们最常用的是userAgent，该属性可以返回由客户机发送的user-agent头部的值。

下面前端代码可以判断用户哪个终端打开界面，实现转跳：

if((navigator.userAgent.match(/(phone|pad|pod|iPhone|ios|iPad|Android|Mobile|BlackBerry|IEMobile|MQQBrowser|JUC|Fennec|WOSBrowser|BrowserNG|WebOS|Symbian|Windows Phone)/i))){

window.location.href=""; //手机

}else{
window.location.href="";//电脑

}

### history对象

window对象给我们提供了一个history对象，与浏览器历史记录进行交互。该对象包含用户（在浏览器窗口中）访问过的URL

+ history.back()可以使用后退功能
+ history.forward()前进功能
+ history.go(参数)前进后退功能 参数如果是1前进一个页面，如果是-1 后退一个页面。

# PC端网页特效

### 元素偏移量offset系列

##### 概述

offset翻译过来就是偏移量，我们使用offset系列相关属性可以动态的得到该元素的位置（偏移）、大小等。

+ 获得元素距离带有定位父元素的位置
+ 获得元素自身的大小（宽度高度）
+ 注意：返回的数值都不带单位

offset系列常用属性：

+ element.offsetParent：返回作为该元素带有定位的父级元素 如果父级都没有定位则返回body
+ element.offsetTop：返回元素相对带有定位父元素上边框的偏移
+ element.offsetLeft：返回元素相对带有定位父元素左边框的偏移
+ element.offsetWidth：返回自身包括padding、边框、内容区的宽度，返回值不带单位
+ element.offsetHeight：返回自身包括padding、边框、内容区的高度，返回值不带单位

##### offset和style区别

offset

+ offset可以得到任意样式表中的样式值
+ offset系列获得的数值是没有单位的
+ offsetWidth包含padding+border+width、
+ offsetWidth等属性是只读属性，只能获取不能赋值
+ 所以，我们想要获取元素的大小位置，用offset更为合适。

style

+ style只能得到行内样式表中的样式值
+ style.width获得的是带有单位的字符串
+ style.width获得不包括padding和border的值
+ style.width是可读写属性，可以获取也可以赋值
+ 所以，我们想要给元素更改值，则需要用style改变

### 元素可视区client系列

##### 概述

client即为客户端，我们使用client系列的相关属性来获取元素可视区的相关信息。通过client系列的相关属性可以动态的得到该元素的边框大小、元素大小等。

##### 系列属性

+ element.clientTop	返回元素上边框的大小
+ element.clientLeft	返回元素左边框的大小
+ element.clientWidth  返回自身包括padding、内容区的宽度、不含边框、返回数值不带单位
+ element.clientHeight  返回自身包括padding、内容区的高度、不含边框、返回数值不带单位

### 立即执行函数

(function(){})()	或	(function(){}())

主要作用：创建一个独立的作用域。

最后的小括号可以视为调用函数

### 元素scroll系列属性

##### 概述

scroll系列的相关属性可以动态的得到该元素的大小、滚动距离等。

##### 属性

+ element.scrollTop	返回被卷去的上侧距离，返回数值不带单位。

+ element.scrollLeft     返回被卷去的左侧距离，返回数值不带单位。
+ element.scrollWidth   返回自身实际的宽度，不含边框，返回数值不带单位。
+ element.scrollHeight    返回自身实际的高度，不含边框，返回数值不带单位。

### 三大系列总结

+ offset系列 经常用于获得元素位置
+ client系列  经常用于获取元素大小
+ scroll系列   经常用于获取滚动距离
+ 注意页面滚动过的距离通过window.pageXoffset获得

### 动画函数封装

##### 动画函数原理

1.获得盒子当前位置

2.让盒子在当前位置加上一个移动距离。

##### 缓动动画

公式（目标值-现在的位置）/10

但是呢会出现小数就要用Math.ceil()往上取整。（注意负数就要向下取整Math.floor()）

# 数据可视化

数据可视化主要是借助图形化手段，清晰有效地传达与沟通信息。

##### 数据可视化的场景

+ 通用报表
+ 移动端图表
+ 大屏可视化
+ 图编辑&图分析
+ 地理可视化

##### 项目目的

市场需求：应对现在数据可视化的趋势，越来越多企业需要在很多场景（营销数据，生产数据，用户数据）下使用，可视化图表来展示体现数据，让数据更加直观。

##### 项目技术

+ HTML5+CSS3布局

+ CSS3动画、渐变
+ jQuery库+原生Javascript
+ flex布局和rem适配方案
+ 图片边框border-image
+ ES6模板字符
+ ECharts可视化库等

### ECharts

ECharts是一个使用Javascript实现的开源可视化库，可以流畅的运行在PC和移动设备上，兼容当前绝大部分浏览器，底层依赖矢量图形库ZRender，直观、交互丰富，可高度个性化定制的数据可视化图表。

##### ECharts使用五步曲

步骤1.下载并引入echarts.js文件——图表依赖这个js库

var name=echarts.init（document.queryselector("div"))

步骤2.准备一个具备大小的DOM容器——生成的图表会放入这个容器

步骤3.初始化echarts实例对象——实例化echarts对象

步骤4.指定配置项和数据——根据具体需求修改配置选项

步骤5：将配置项设置给echarts实例对象——让echarts对象根据修改好的配置生效

### 适配方案

flexible.js——检测浏览器宽度，修改html文字大小。

rem单位——页面元素根据rem适配大小配合cssrem插件

flex布局

### 边框图片

这个是css3的

相当于你空洞骑士里面的那个花边

##### 边框图片语法

+ border-image-source——用于边框图片的路径
+ border-image-slice——图片边框向内偏移（裁剪的尺寸，不加单位）
+ border-image-width——图片边框的宽度（不是边框的宽度是边框图片的宽度）加单位
+ border-image-repeat——图片是否平铺、铺满、拉伸。
