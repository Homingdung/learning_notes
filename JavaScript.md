# JavaScript

# 简介

三部分组成：

ECMAScript

DOM

BOM



JS：

+ 解释型语言（写完不用编译，直接运行）
+ 类似于C和java的语法结构
+ 动态语言
+ 基于原型的 **面相对象**



Alert/ document.write/ console.log

```html
<script type="text/javascript">
  //js 代码
  alert("我是弹出框的内容")
  document.write("我是body里面的内容")
  console.log("我是控制台里面的内容")//从上到下按顺序执行
</script>
```

```html
<button onclick="alert('你刚刚点了我')">点击我</button>
<a href="javascript:alert('让你点你就点')">你也点我</a>
<a href="javascript:;">你也点我</a>
```

外部js文件：

```html
<script type="text/javascript" src="路径"></script>
```



注意：Script 标签，用于引入外部文件，就不能在内部编写了；如果需要，则再创建一个新的script

# JavaScript基本语法

单行注释：//

多行注释：/* */

Js中严格区分大小写

每一条语句以分号（；）结尾（如果不写分号，浏览器会自动添加，但是会消耗一些系统资源，有些时候会加错分号）

Js中会忽略多个空格和换行，所以我们可以利用空格和换行对代码进行**格式化**



# 字面量和变量

字面量：都是不可改变的值，比如：1 2 3 4 5 ，可以直接使用，但一般都不直接使用字面量

变量：可以用来保存字面量，而且变量可以任意改变的，开发中都是通过变量去保存一个字面量，很少使用变量

声明变量：var

声明但没赋值后是undefined

```js
var a = 123;
console.log(a);
```



# 标识符

Js中所有可以自主命名的都可以称为标识符

规则：

1 标识符中可以含有字母，数字，_, $

2 标识符不能以数字开头

3 标识符不能是ES中的关键字或保留字

4 标识符一般用驼峰命名法：首字母小写，每个单词的开头字母大写，其余字母小写

5 JS底层保存标识符时实际上用的是Unicode编码，理论上讲，utf-8都可以



# 字符串

数据类型指的就是字面量的类型

Js中一共六种数据类型

+ String 字符串

+ Number 数值

+ Boolean 布尔值

+ Null 空值

+ Undefined 未定义

+ Object 对象



String Number Boolean Null Undefined属于基本数据类型，Object属于引用数据类型

+ 字符串需要用**引号**引起来

+ 双引号单引号都行，但是不要混着用
+ 引号不能嵌套，双引号里面不能放双引号，单引号里面不能放单引号
+ 字符串中可以用 \ 作为转义字符

```js
var str="hello";
var str="我说：'早上好'"
var str="我说：\"早上好\""

\n 换行
\t 制表符 tab
\\ 表示\
```



# 数值

Js中所有的数值都是Number类型

包括正数和浮点数（小数）

**typeof**：检查变量类型

Js中表示数值最大值，最小值

```js
console.log(Number.MAX_VALUE)//1.7976931348623157e+308
console.log(Number.MIN_VALUE)//5e-324
```

Infinity: 正无穷，本身是一个字面量，不加引号，也是Number

-Infinity：负无穷

NaN：特殊数字，表示 Not a Number

Js 进行浮点数计算，可能得到一个不精确的结果，所以不要使用Js进行精确度比较高的运算



# 布尔值

布尔值只有两个：true 逻辑真 false 逻辑假，布尔值用来做逻辑判断，**不加引号**



# Null和Undefined

Null：

+ Null只有一个值，就是null

+ null专门用来表示一个为空的对象

+ 使用typeof（）返回object

Undefined：

+  只有一个值，就是undefined
+ **声明一个变量但不赋值**，就是undefined
+ 使用typeof（）返回undefined



# 强制类型转换String

将一个数据类型强制转换为其他数据类型

类型转换主要指，将其他的数据类型转换为String Number Boolean



强制转换为String：

```js
var a=123;
console.log(typeof a);//number
console.log(a);//123
//方式1：调用被转换数据类型的toString（）方法 ，调用xxx的yyy方法，xxx.yyy（）
//调用a的toString
//null undefined两个值没有toString，如果调用他们的方法，会报错
a.toString（）；//会有返回值，返回值就是结果
a = a.toString();
//方法2:
//调用String（）函数，并将被转换的数据作为参数传递给函数
//使用String（）函数，对于Number和Boolean实际上就是调用toString（）方法，但对于Null和undefined，不回调用toString（）方法了，它会将null直接转换成"null"，将undefined直接转换成"undefined"
a = 123;
a = String(a);//要赋值
```

# 强制类型转换Number

转换方式1:

Number（）函数

```js
var a = "123"
a = Number(a)
```

1. 如果是纯数字字符串，直接将其转换为字符串;
2. 如果是字符串中有非数字内容，转换为NaN;
3. 如果为空，转为0；
4. 如果是布尔值，true 转为 1，false转为 0;
5. 如果是 null，转为 0；
6. 如果是undefined，转为NaN；

```js
var a = "123";// Number(typeof(a))输出Number；
var a = "123abc";//Number(typeof(a))输出Nan；
var a = "";//Number(typeof(a))输出0；
var a = true;//Number(typeof(a))输出1,false则输出0；
var a = null;//Number(typeof(a))输出0；
var a = undefined;//Number(typeof(a))输出NaN；
```

转换方式2:

专门用来对付字符串；

parseInt（）函数：把一个字符串转换为一个**整数**，将字符串中的有效的整数内容取出来,然后转换为 Number；

```js
var a = "123abc";//parseInt(a)输出 123；
```

parseFloat（）作用和parseInt（）类似，不同的是它可以获得有效的小数；

```js
var a = "123.456px";//parseFloat(a）输出123.456
```

如果对String使用parseInt（）或parseFloat（），它会先将其转换为String然后操作；

# 其他进制的数字

JavaScript 最后以十进制输出；

16进制：0x开头；

8进制：0开头；

2进制：0b开头，但有些浏览器不支持；

譬如“070”这种字符串，有些浏览器会当作8进制解析，有些会当作10进制解析；

可以在parseInt（）中传递第二个参数，指定数字进制；

```js
a = "070";
a = parseInt(a,10);//70
```



# 转换为 Boolean

Boolean（）函数:

+ 数字->布尔值：除了0 NaN，其余都是true

```js
var a = 123;
a = Boolean(a);
console.log(typeof(a));//输出 true
```



# 算数运算符

+ 运算符可以对一个或多个值进行运算，并获取结果

+ typeof 就是运算符，获得一个值的类型，它会将给值的类型以字符串的形式返回

```js
var a = 123;
var result = typeof a;
console.log(typeof result);//输出string;
```

算数运算符：

+ 非Number运算，会先转换成Number再运算（true->1,null->0）
+ 任何值和NaN做运算，结果都是NaN
+ 两个字符串做加法，则会做**拼接**
+ **任何值和字符串做加法**，先转成字符串然后相加（拼接），利用这个特点，只需将任意数据类型+一个""即可将其转换为String，这是一种隐式类型转换，由浏览器自动完成，实际上也是调用了String（）
+ 除了加法，其余运算都会先转换成Number

```js
+ 加
- 减
* 乘
/ 除
% 模（余数）

```

较长字符串,可以用加号换行拼接：

```js
var str="锄禾日当午,"+
        "汗滴禾下土,"+
   			"谁知盘中餐,"+ 
    		"粒粒皆辛苦";
```



# 一元运算符

之前讲的是二元运算符，

+ 正号不变
+ 负号取反
+ 对非Number值，先转成Number，可以对一个其他的数据类型使用+，转换成Number

```js
var a = 123;
a = +a;//正号不变
a = -a;//取反
```

# 自增和自减

+ 自增可以使变量在自身的基础上增加1

+ 变量自增以后，原变量的值会立即自增1
+ 自增两种：后++（a++）和前++（++a），无论是a++，还是++a，都会立即使原变量的值自增1，不同的是a++ 和++a的值不同：
+ a++的值等于原变量的值（自增前的值）；++a的值等于原变量的新值（自增后的值）

```js
var a = 1;
a++//自增1

var c = 10;
//第一次c++，是在10的基础上自增
c++;
//第二次c++，是在11的基础上自增
c++;
console.log(c++);//12

var d = 20;
console.log(++d);//21
console.log(++d);//22

var d = 20;
var result = d++ + ++d + d;//64
// 20 + 22 + 22
```

+ 自减两种：后--（a--）和前--（a--），都会立即使原变量的值自减1，不同的是a--和--a的值不同
+ a--是原变量的值；--a的值是原变量的新值

```js
var n1 = 10, n2 = 20;
var n = n1++;//n1 = 11 n1++ = 10
console.log('n='+n);//10
console.log('n1='+n1);//11

n = ++n1//n1 = 12 ++n1 = 12
console.log('n='+n);//12
console.log('n1='+n1);//12

n = n2--;//n2 = 19 n2-- = 20
console.log('n='+n);//20
console.log('n2='+n2);//19

n = --n2;//n2 = 18 --n2 = 18
console.log('n='+n);//18
console.log('n2='+n2);//18
//一定要搞清楚原值是多少，在谁的基础上运算
```



# 逻辑运算符

三种逻辑运算符：

```js
! 非 取反操作 //true->false false->true
&& 与
|| 或
```

```js
var a = true;
a = !a;
console.log(a)//false;

var b = 10;
b = !b;
console.log("b="+b);//b=false
console.log(typeof b);//boolean

```

！非：

+ 对一个值两次取反，不会变化
+ 对非布尔值运算，则会将其先转换为布尔值，然后取反，可以为一个任意数据类型取两次反，将其转换为布尔值类型

&& 与：

+ 两个值只要有一个为false，就会返回false
+ 短路“与”：只要第一个值false，不会检查第二个值

```js
var result=true&&true;
console.log(result)//true

var result=true&&false;//false
var result=false&&true;//false
var result=false&&false;//false
```



｜｜或：

+ 两个值只要有一个true，就返回true
+ 两个值都为false，才返回false

```js
var result=true&&true;
console.log(result)//true

var result=true&&false;//true
var result=false&&true;//true
var result=false&&false;//false
```





# 非布尔值的逻辑运算

与运算：

+ 非布尔值的运算，会先转换为布尔值，然后再运算，并且返回原值（即不回返回 true或者 false）
+ 如果两个值都为true，返回后边的数
+ 如果两个值有false，返回靠前的false
+ 以上规则符合**断路**情况
+ 如果第一个值为 true，则返回第二个值
+ 如果第一个值为false，则返回第一个值
+ 与运算找false

```js
var result=1 && 2;
console.log(result);//2（第二个值）

var result=0 && 2;
console.log(result);//0

var result=NaN && 0;
console.log(result);//NaN（第一个值）
```

与此相反：



或运算：

+ 如果第一个值为true，则直接返回第一个值
+ 如果第一个值为false，则直接返回第二个值
+ 或运算找true

# 赋值运算符

=：

+ 可以将等号右侧的值赋值给左侧的变量

+=：

-=：

*=:

/=:

%=:

```js
a=a+5;
a+=5;//两者等价
```

# 关系运算符

+ 通过关系运算符比较两个值的大小关系
+ 成立返回true
+ 不成立返回false

```js
>;
<;
>=;
<=;
var result=5>10;
console.log(result);//false
```

非数值情况：

+ 非数值比较，先转换成数字再比较
+ 任何值和NaN比较，都是false
+ 符号两侧都是字符串，不会将其转化为数字，分别比较字符Unicode字符编码
+ 比较字符编码是一位一位进行比较；两位相同，则比较下一位，所以借用这个对英文排序，比较中文没有意义
+ 如果比较两个字符串型数字，可能得到不可预测的结果，注意比较两个字符串的数字，一定要**转型**

```js
console.log(1>=true);//false
console.log(1>"0");//true
console.log(10>null);//true
console.log(10>"hello");//true
console.log(true>false);//true 1>0
console.log("11"<"5");//true 都是字符串,比较Unicode编码
console.log("abc"<"b")//true
```

# Unicode编码表

网页中使用Unicode编码，&#编码；编码需要十进制

```html
<h1 style="font-size":200px;>&#9760</h1>
<!--要转换为十进制>
```


```js
console.log("\u2620");//骷髅头☠️
```

# 相等运算符

+ 比较两个值是否相等；相等返回true，不相等返回false
+ 当使用==比较两个值，值类型同，会自动类型转换
+ Undefined 衍生自null，所以这两个值做相等判断时，会返回
+ 可以通过 isNaN（）函数，判断一个值是否是NaN, 是返回true，不是返回false
+ != 来做不相等运算
+ var a = 123;
  a = Boolean(a);
  console.log(typeof(a));//输出 true
+ === 全等，不做类型转换
+ ！==不全等
```js
console.log(1==1);//true

var a==10;
console.log(a==4);//false

console.log("1"==1);//true

console.log(true=="1");//true

console.log(null==0);//false

console.log(undefined==null);
console.log(NaN==NaN);//NaN 不和任何值相等，包括他本身

var b=NaN;
console.log(isNaN(b));//true

console.log(10!=5);//true
console.log(10!=10);//false
console.log("123"===123)；//false

console.log(1!==1);//true
```



# 条件运算符（三元运算符）

？:

```js
条件表达式：？语句1:语句2；
```

+ 条件运算符在执行时，首先对条件表达式进行求值：如果位true，执行语句1；如果为false，执行语句2
+ 有返回值
+ 条件运算是非布尔值，先转换

```js
true?alert("语句1")：alert("语句2")；

a>b?alert("a大"):alert("b大")；

//获取a b中最大值
var max=a>b?a:b;
console.log(max);//谁大返回谁
//获取 a b c 中最大值
var max>c?max:c;
//嵌套比较
var max=a>b?(a>c?a:c):(b>c?b:c);
console.log(max);//写法不推荐，不易阅读
```



# 运算符优先级

+ ， 运算符，可以分割多个语句，声明多个变量时使用

```js
var a=1, b=2, c=3;
alert(b);
```

+ 和数学一样，JS也有运算优先级
+ 如果遇到优先级不确定，用（）

```js
var result=1 || 2 && 3;
console.log(result);//1
```

+ 语句按照从上倒下一条一条执行，JS可以用{}来分组，同一个{}中的语句，为一组，要么执行要么不执行，一个{}叫做一个**代码块**
+ 代码块内部的在外部可见
+ 代码块后面不用写；

```js
{
  var a=10
  alert("hello")
  console.log("你好")
  document.write("语句")
}
```

# 流程控制语句

+ 通过流程控制语句可以控制程序执行流程
+ 语句分类
  + 条件判断语句
  + 条件分支语句
  + 循环语句



条件判断语句：

+ 成立，执行；不成立，不执行
+ if语句
+ if会对条件表达式进行求值判断
+ if后面的代码块不是必须的，但是开发中尽量写

```js
if(条件表达式){
  	语句1
    语句2
   }//代码块
//条件表达式true，执行；false，不执行

var age=60;
if (age>=60){
  alert("你已经退休了")
}
```
```js
if(条件表达式){
  语句1
   
}else{
  语句2
  
}

var age=60
if (age>=60){
  alert("你已经退休了")
}else{
  alert("你没有退休")
}
```
```js
  
if(条件表达式){
  语句1
   
}else if(条件表达式){
  语句2
  
}else if(条件表达式){
  语句3
}else{
  语句4
}//所有条件都不满足，执行else后面语句
```



Prompt()可以弹出一个提示框，提示框中可以输入

```js
var content = prompt("请输入你想要的内容");
console.log(content);
```



条件分支语句：

+ switch语句
+ switch执行时会依次将case后的表达式的值和switch后的条件表达式的值进行全等比较
+ 由于case后面的都会执行，所以加一个break退出当前case
+ 所有比较结果都是false，执行default后的语句

```js
switch(条件表达式){
  case 表达式:
    语句
    break;
  case 表达式:
    语句
    break;
  default:
    语句
    break;
}
```



while循环：

+ true,执行循环；false，终止循环
+ 三个步骤：
  + 创建一个初始化变量
  + 循环中设置一个条件
  + 定义一个更新表达式，每次更新初始化变量

```js
while(条件表达式){
  语句
}

var i=0;
while(i<10){
  i++
}
```

do... while循环：

+ 先执行循环体，再判断，为true，继续循环，为false，终止循环
+ 保证循环体至少执行一次

```js
do{
  语句
  
}while();
       

```



for循环：

```js
for(初始化表达式；条件表达式；更新表达式){
  语句
}
```

```js
for(var i=1;i<=10;i++){
  alert(i);
}
```



嵌套for循环：

```js
//输出图形*
for (var i=0;i<5;i++){
  for (var j=0;j<5;i++){
    document.write("*");
    
  }
  document.write("<br />");
}
```

# break和continue

break：

+ break关键字用来退出switch或循环语句
+ 不能在 if 语句中使用 break 和 continue

+ 可以为循环语句创建一个 label，标识当前循环，这样break将会终止指定的循环，而不是就近的

```js
outer:
for (var i=0;i<5;i++){
  console.log("@外层循环"+i)
  for (var j=0;j<5;j++){
    break outer;
    console.log("@内层循环"+j);
  }
}
//@外层循环0
```



continue：

+ 跳过当次循环
+ continue只会对最近的循环起作用

```js
for(var i=0;i<5;i++){
  console.log(i);
  if(i==2){
    continue;
  }
  console.log(i);
}
```



计时器：

+ 测试程序性能
+ 程序执行之前，开启计时器
+ console.time("计时器名字")用来开启一个计时器
+ 需要一个字符串参数，这个字符串将会作为计时器的标识

+ console.timeEnd("计时器名字")

```js
console.time("test");
//程序代码
//...
//...
console.timeEnd("test");
```



# 对象

数据类型：

+ String 字符串
+ Number 数值
+ Boolean 布尔值
+ Null 空值
+ Undefined 未定义
  + 以上五种类型属于基本数据类型，只要不是以上五种，都是对象
+ Object 对象



引入：

+ 基本数据类型识单一的值，值和值之间没有任何的联系
+ 所创建的变量都是独立的，不是一个整体
+ 对象是一个复合数据类型，在对象中可以保存多个不同数据类型的属性

对象分类：

1. 内建对象：由 ES 标准中定义的对象，在任何的 ES 的实现中都可以使用，比如 Math String Number Boolean Function Object...
2. 宿主对象：由 JS 运行环境提供的对象，目前来说主要指由浏览器提供的对象，比如 BOM DOM
3. 自定义对象：开发人员自己创建的对象

基本操作：

+ 使用 new 关键字调用的函数，是构造函数 construtor
+ 构造函数是专门用来创建对象的函数
+ typeof 检查，返回 object
+ 对象中保存的值称为**属性**
+ 语法：**对象.属性名=属性值**

```js
var obj = new object();
obj.name="孙悟空";
obj.gender="男";
obj.age=18;
console.log(obj);
```

+ 读取对象属性： 对象.属性名
+ 读取对象中没有的属性，不会报错，会返回 undefined
+ 删除对象属性：delete 对象.属性名



属性名：

+ 属性名不强制要求遵守标识符的规范
+ 特殊属性名，用: 对象["属性名"] = 属性值，读取也要用这种方式
+ 使用[]更加灵活，在[]中可以直接传递一个变量，这样的变量是多少就会读取那个属性

属性值：

+ 可以是任意数据类型
+ 也可以是对象嵌套
+ in 运算符，可以检查一个对象中是否有指定属性，有返回 true，没有返回 false
+ 语法："属性名" in 对象



# 基本数据类型和引用数据类型

+ JS 变量保存在栈内存里，值与值独立存在
+ 对象保存在堆内存中，每创建一个新对象，就会在堆内存里开辟一个新的空间，而变量保存的是对象的内存地址（对象的引用），如果两个变量保存的是同一个对象引用，当一个通过一个变量修改属性时，另一个也会受到影响
+ 当比较两个基本数据类型的值时，就是比较值
+ 当比较两个引用数据类型时，比较对象的**内存地址**：如果连个对像是一模一样的，但地址不同，它也会返回 false

# 对象字面量

+ new object 创建对象

+ 使用对象字面量创建对象

```js
var obj = {};
console.log(obj);
```

多个属性：

+ 对象字面量可以加引号也可以不加
+ 如果使用一些特殊名字，必须加引号
+ 属性名和属性值是一组一组的名值对结构，名和值之间使用冒号连接，多个名值对之间，逗号隔开，最后一个属性不加逗号


```js
var obj2 = {
  name:"Tom",
  age = 18, 
  gender="male",
  test:{name:"John"}
};
```



# 函数

+ 函数也是一个对象
+ 函数可以封装一些功能，需要时可以执行这些功能
+ 函数中可以保存一些代码在需要时调用
+ 函数具有普通对象所有功能

**构造创建一个函数对象**：

```js
var fun = new Function();//很少用
```

+ 封装到函数中的代码不会立即执行
+ 调用时才会执行
+ 调用语法：对象（）；
+ 调用函数，按顺序执行

```js
fun();
```

**函数声明创建函数**：

```js
function 函数名（[形参1，形参2....形参N]）{
  语句
}
```

```js
function fun2(){
  console.log("function2");
}
fun2();
```

**使用函数表达式创建函数**：

```js
var 函数名 = function ([形参1，形参2....形参N]){
  语句
}
```

```js
var fun3 = function(){
  console.log("function3")
};
```





定义一个用来求和的函数：

+ 在函数（）中指定一个或者多个形参（形式参数），逗号隔开，声明形参，但是并不赋值
+ 调用函数解析器不会检查实参的类型，也不会检查数量，多余的参数不会被赋值
+ 如果没有对应的实参，形参则是undefined

```js
function sum(x,y){
 	console.log(x+y);
}
```



# 函数的返回值

求和函数：

```js
function sum(a,b,c){
  alert(a+b+c);
}
sum();
//没有返回值
```



return返回值：

+ return 后面的值将会作为函数执行的结果返回
+ 可以定义一个变量，接受这个值

+ return后面不跟值，相当于一个 undefined；不写 return，也是 undefined
+ return 后面可以跟任何类型的值

```js
function sum(a,b,c){
  var d= a+b+c;
  return d;
}
sun();

var result=sum(4,7,8);//result 是 19
```



立即执行函数：

+ 定义完立即调用，立即执行函数
+ 往往只会执行一次

```js
(function(){
  alert("匿名函数")
})();
```

```js
(function(a,b){
  console.log(a);
  console.log(b);
})(123,456);
```

# 方法

+ 对象属性值也可以是函数

```js
var obj = new Object();
obj.name="孙悟空";
obj.age=18;
obj.sayName=function(){
  console.log(obj.name);
}
obj.sayName();//调用方法
```

+ 如果函数作为对象属性保存，那么这个函数叫做对象的**方法**
+ **调用函数**和**调用方法**只是名称上的区别, 没有本质差别



枚举对象属性：

+ for...in 语句
+ 有几个属性循环体执行几次

```js
var obj = {
  name:"孙悟空",
  age:18,
  gender:"男",
  address:"花果山"
}

for (var 变量 n in 对象){
}

for (var n in obj){
  console.log(obj[n]);
}
```

# 全局作用域

作用域：

+ 一个变量作用的范围
+ JS两种作用域：
  + 全局作用域
    + 直接编写在 script 标签中的 JS 代码，都在全局作用域
    + 全局作用域在页面打开时创建，页面关闭时销毁
    + 在全局作用域中有一个全局对象 window，代表浏览器窗口，由浏览器创建，可以直接使用
    + 全局作用域中:
      + 创建的**变量**都会作为 window 对象的**属性**保存
      + 创建的**函数**都会作为 window 对象的**方法**保存
  + 函数作用域
+ 全局作用域中的变量都是全局变量，页面任何部分都可以访问到



```js
var a=10;
console.log(window.a);//全局作用域中，创建的变量都会作为 window 对象的**属性**保存

function fun(){
  console.log("This is function")
}
window.fun();//创建的函数都会作为 window 对象的**方法**保存
```



变量声明提前：

+ 使用 var 关键字声明的变量，会在所有的代码执行之前被声明，但是不会赋值
+ 如果声明变量不使用 var 关键字，则变量不会被声明提前
+ 函数的声明提前：
  + 使用函数声明形式创建的函数 function 函数名 (){}
    + 会在所有代码执行之前就被创建，优先解析，所以可以在函数声明前调用函数
  + 使用函数表达式创建的函数，不会被声明提前，所以不能在声明前调用

```js
//函数声明会被提前创建
fun();
function fun(){
  console.log("this is function")
}

//函数表达式不会被提前创建
var fun2 = function(){
  console.log("this is function2")
}
fun2();
```



函数作用域：

+ 调用函数时创建函数作用域，函数执行完毕后，函数作用域销毁
+ 每调用一次函数就会创建一个新的函数作用域，之间互相独立
+ 函数作用域中可以访问到全局作用域变量，全局作用域无法访问到函数作用域
+ 当在函数作用域中操作一个变量时，会先在自身作用域中寻找，如果有就直接使用，否则去上一级中寻找，一直会找到全局作用域，如果仍旧没找到，会报错
+ 函数中想访问全局变量，使用 window.变量名
+ 函数作用域中也有声明提前的特性：
  + 使用 var 关键字声明的变量，会在函数中所有的代码执行之前被声明
  + 函数中不使用 var 声明的变量都会成为全局变量
+ 定义形参相当于声明了变量

```js
var a = 10;
function fun(){
  var a = "函数中的变量 a "//就近原则
  var b = 20;
  console.log(a);
}
fun();
console.log(b)//b is not defined
```



# JS中的 this

+ 调用函数时，每次都会向函数内部传递一个隐含的参数, 这个隐含的参数就是 this
+ this 指向的是一个对象，这个对象我们称为函数执行的上下文对象
+ 根据函数的**调用方式**(和创建方式没有关系)的不同，this 会指向不同的对象
  + 以函数的形式调用，this 永远都是 window
  + 以方法的形式调用，this 就是调用方法那个对象

```js
function fun(a,b){
  console.log("a,b")
};
fun(123,456);

function fun(a,b){
  console.log(this);
};
fun(123,456);
//[object Window]
```



例子：

```js
//创建一个 name 变量
var name = "全局"；
// 创建一个 fun（）函数

function fun(){
  console.log(this.name)//动态变化
}

var obj={
  name:"孙悟空",
  sayName:fun
}


var obj={
  name:"沙和尚",
  sayName:fun
}

obj.sayName();//孙悟空
obj2.sayName();//沙和尚
```



工厂方法创建对象：

+ 大批量创建对象
+ 使用工厂方法创建的对象，使用构造的函数都是object，导致无法区分多种不同的对象



```js
function cretePerson(name,age,gender){
  //创建对象
  var obj=new object();
  //向对象中添加属性
  obj.name=name;
  obj.age=age;
  obj.gender=gender;
  obj.sayName=function(){
    alert(this.name);
  }
  //将新的对象返回
  return obj;
  
}
var obj1=createPerson("孙悟空",18,"男");
var obj2=createPerson("猪八戒",28,"男");
var obj3=createPerson("沙和尚",38,"男");
console.log(obj1);
console.log(obj2);
console.log(obj3);
```

构造函数：

+ 创建一个构造函数，专门用来创建 Person 对象的
+ 构造函数就是一个普通的函数，创建方式和普通函数没有区别，构造函数习惯上首字母大写
+ 构造函数和普通函数区别就是调用方式不同
+ 普通函数是直接调用，构造函数需要使用 **new** 关键字来调用
+ 构造函数的执行流程
  1. 立刻创建一个新的对象
  2. 将新建的对象设置为函数中的 this，在构造函数中可以使用 this 来引用新建的对象
  3. 逐行执行函数中的代码
  4. 将新建的对象作为返回值返回

+ 使用同一个构造函数创建的对象，我们称为一类对象，也将一个构造函数称为一个类，我们将通过一个构造函数创建的对象，称为是该类的实例



```js
function Person(name,age,gender){
  	this.name=name,
 		this.age=age,
    this.gender=gender
    
}
var per = new Person("孙悟空"，18，"男");
console.log(per);
```

+ 使用 instanced 可以检查一个对象是否是一个类的实例,是返回true，不是返回false
+ 任何对象和 object 做 instanceof检查返回都是true

```js
console.log(per instanceof Person);
```



# 原型对象

+ 将函数定义在全局作用域，污染了全局作用域命名空间
+ 而且全局作用域中很不安全

原型（prototype）：

+ 创建的每一个函数，解析器都会向函数中添加一个属性 prototype，这个属性对应了一个对象，这个对象就是所谓的原型对象
+ 如果函数作为普通函数调用 prototype，没有任何作用
+ 当函数以构造函数的形式调用时，它所创建的对象中会有一个隐含的属性，指向构造函数的原型对象，我妈可以通过_proto_来访问该属性
+ 原型对象相当于**公共区域**，所有同一个类的实例可以访问到这个原型对象，可以将对象中的共有内容，统一设置到原型对象中
+ 当访问对象的一个属性或者方法时，它会先在对象自身中寻找，如果有则直接使用；没有，会去原型对象中去寻找

```js
function MyClass(){
  
}
//向Myclass的原型中添加属性a
MyClass.prototype.a = 123;
var mc=new MyClass();
var mc2=new MyClass();
mc.a = "我是mc中的a"
console.log(mc2.a);//123

```



+ 构造函数可以将这些对象共有的属性和方法统一添加到构造函数的原型对象中，这样不用分别为每一个对象添加，也不会影响到全局作用域，就可以使每一个对象都具有这些属性和方法了

```js
//创建一个构造函数
function MyClass(){
}
MyClass.prototype.name = "我是原型中的名字"

var mc = new MyClass();
console.log(mc.name);
//使用 in 检查对象中是否含有某个属性时，如果对象中没有但是原型中有，也会返回 true
console.log("name" in mc);
//检查对象自身中是否有该属性
console.log(mc.hasOwnProperty("age"));

```



+ 原型对象也是对象，所以它也有原型
  + 使用一个对象属性或者方法时，会在自身中寻找
    + 自身中有，直接使用
    + 如果没有则去原型对象中寻找，如果原型对象中有，则使用
    + 如果没有则去原型的原型中寻找，直到找到object原型，如果object没有找到，返回undefined





toString（）

```js
function Person(name,age,gender){
  this.name = name;
  this.age = age;
  this.gender = gender;
}
//修改 Person 原型的 toString
Person.prototype.toString = function(){
  return "Person"[name,age,gender]
};
//创建一个Person实例
var per = new Person("孙悟空",18,"男")；
//直接在页面打印一个对象时，实际上是输出的对象的toString（）方法的返回值
console.log(per.toString());//[object object]
console.log(per);
```



# 垃圾回收（GC）

+ 程序运行过程中会产生垃圾，导致程序运行过慢
+ 垃圾回收机制处理运行过程中的垃圾
+ 当一个对象没有任何变量和属性对它进行引用，此时我们将永远无法操作该对象，这种对象就是一个垃圾，占用大量内存，导致程序运行过慢，需要清理
+ JS中拥有自动垃圾回收机制，自动将垃圾对象从内存中销毁，我们不需要也不能进行垃圾回收的操作，只需要把不需要使用的对象设置为null即可

``` js
var obj = new object();
//对对象进行各种操作...
obj = null;
```



# 数组

对象：

+ 内建对象
+ 宿主对象
+ 自定义对象



数组（Array）：

+ 数组也是一个对象
+ 和普通对象功能类似，也是用来存储一些值的
+ 不同的是普通对象
+ 索引：
  + 从0开始的整数就是索引
  + 数组的存储性能比普通对象好，在开发中我们经常使用数组来存储一些数据

创建数组对象：

```js
var arr = new Array();
console.log(typeof arr);//object
```

向数组添加元素：

```js
arr[0] = 10;
arr[1] = 30;
```

读取元素：

```js
arr[0];
arr[1];
//读取不存在返回 undefined
```

获取数组长度：

+ 使用length属性

+ 非连续数组（跳过了某些索引），使用length会获取最大的索引

+ 修改length：

  + 如果修改的length大于原长度，则多出的部分会空出来
  + 如果修改的length小于原长度，则多出的元素会被删除

  

```js
console.log(arr.length);
```

+ 向数组最后一个位置添加元素(小技巧)

```js
arr[arr.length]=70;//永远向数组最后一位置添加
```



数组字面量：

+ 字面量创建数组：

+ 语法：[]

```js
var arr = [];
console.log(typeof arr);
```

+ 字面量创建数组，创建时就可以指定数组中的元素

```js
var arr = [1,2,3,4,5,10];
```

+ 元素之间用逗号隔开：

```js
var arr2 = new Array(10,20,30);
```

+ 创建一个数组中只有一个元素10

```js
arr = [10];
```

+ 创建一个长度为10的数组：

```js
arr2 = new Array(10);
console.log(arr2.length);
```

+ 数组中的元素可以是任意的数据类型，也可以是对象，也可以是函数

```js
arr = ["hello",1,true,null,undefined];
var obj = {name:"孙悟空"};
arr[arr.length] = obj;//对象
arr = [function(){alert(1)},function(){alert(2)}];//函数
arr = [[1,2,3],[3,4,5],[5,6,7]];//数组 二维数组
```

数组的四个方法：

push ():

+ 可以向数组中添加一个或者多个元素，并返回数组新的长度
+ 要添加的元素作为方法的参数，这样这些元素将会自动添加到数组的末尾
+ 该方法会将数组新的长度作为返回值

```js
var arr = ["孙悟空","猪八戒","沙和尚"];
arr.push("唐僧","蜘蛛精","白骨精");
console.log(arr);
```

```js
var result = arr.push("唐僧","蜘蛛精","白骨精");
console.log(result);//6
```



pop ():

+ 该方法可以删除数组的最后一个元素
+ 被删除的元素是返回值



unshift():

+ 向数组开头添加一个或多个元素，并返回数组长度
+ 向前边加入元素，其他元素的索引会依次调整



shift（）：

+ 可以删除数组的第一个元素，并将被删除的元素作为返回值



数组的遍历：

+ 遍历数组就是把数组所有元素都取出来

```js
var arr = ["孙悟空","猪八戒","沙和尚"];
console.log(arr[0]);
console.log(arr[1]);
console.log(arr[2]);//太繁琐

for(var i = 0;i<arr.length;i++){
  console.log(arr[i]);
}
//i是 index 的简写
```



forEach方法：

+ 一般用for循环遍历数组，JS提供了一个方法 forEach（）
+ 这个方法只支持**IE8**以上的浏览器, IE8（不支持）及以下用 for遍历
+ 需要传递一个函数

```js
var arr = ["孙悟空","猪八戒","沙和尚"];
arr.forEach(function(){
  console.log("hello");
});
```

forEach()方法需要一个函数作为参数

+ 由我们创建但不由我们调用，称为回调函数

+ 数组中有几个元素就会执行几次，每次执行，浏览器都会将遍历到的元素以实参形式传递回来，我们可以定义形参来读取这些内容

+ 浏览器会在回调函数中传递三个参数

  + 第一个参数，就是当前正在遍历的元素
  + 第二个参数，就是当前正在遍历的元素的索引
  + 第三个参数，就是当前正在遍历的数组

  ```js
  arr.forEach(function(value,index,obj){
    console.log(value);
    console.log(index);
    console.log(obj);
  })
  ```

  

  

slice （）和 splice（） 方法：

slice（）：

+ 可以用来从数组中提取指定元素
+ 该方法不会改变原数组，而是将截取到的元素封装到一个新数组中返回

+ 参数：
  + 截取开始位置的索引，**包含开始索引**
  + 截取结束位置的索引，**不包含结束索引**
    + 第二个参数可以省略不写，此时截取从开始索引后的所有元素
  + 索引可以传递负值，则从后往前计算，-1:倒数第一个，-2:倒数第二个

```js
var arr = ["孙悟空","猪八戒","沙和尚"];
result = arr.slice(0,1);//需要接受返回值
console.log(result);//孙悟空
```

splice（）：

+ 删除数组中的指定元素
+ 会影响到原数组，会将指定元素从元素组中删除，并将被删除的元素返回
+ 参数：
  + 第一个，表示开始位置索引
  + 第二个，删除数量
  + 第三个及以后，可以传递新的元素，这些元素将会自动插入到开始位置索引的前边



concat（）方法：

+ 连接两个或多个数组，并将新的数组返回
+ 不会对原数组产生影响
+ 还可以传单个元素

```js
var arr = [];
var arr2 = [];
var arr3 = [];
var result = arr.concat(arr2,arr3);
console.log(result);
```



join（）方法：

+ 将数组转换为一个字符串
+ 不会对原数组产生影响，转换后的字符串返回
+ join（）中可以指定一个字符串作为参数，这个字符串将会成为数组中元素的连接符，不使用默认为逗号

```js
var arr = ["孙悟空","猪八戒","沙和尚"];
result = arr.join("@@");
console.log(result);//孙悟空@@猪八戒@@沙和尚
```



reverse()方法：

+ 用来反转数组
+ 对原数组有影响



sort（）方法：

+ 数组中对元素排序
+ 对原数组有影响
+ 按unicode编码进行排序
+ 即使是纯数字数组，使用sort（）也会按照unicode编码排序，数字排序可能会得到错误结果
+ 指定排序规则：
  + sort（）中添加一个回调函数，来指定排序规则
  + 浏览器将会分别使用数组中的元素作为实参去调用回调函数
  + 使用哪个元素不确定，但是肯定的是在数组中a一定在b前面
    + 如果返回一个大于0的值，则元素会交换位置
    + 如果返回一个小于0的值，则元素位置不变
    + 如果返回0，认为两元素相等，不变
    + 更简便方法：
      + 需要升序，返回 a-b
      + 需要降序，返回b-a

```js
arr=[5,4];
arr.sort(function(a,b){
  //前面的大 
  if(a>b){
    return 1;
  }else if(a<b){
    return -1;
  }else{
    return 0;
  }
})

arr.sort(function(a,b){
  return a-b;
})
```



Call（）和apply（）方法  ：

+ 都是函数对象的方法，需要通过函数对象来调用

```js
fun.apply();
fun.call();
fun();
```

+ 调用call（）和apply（）可以将一个对象指定为第一个参数，此时这个对象会成为函数执行的this

+ call方法可以将实参在对象之后依次传递
+ apply方法需要将实参封装到一个数组中统一传递

```js
fun.call(obj,2,3);
fun.apply(obj,[2,3]);
```

+ this:
  + 以函数形式调用，this永远都是window
  + 以方法形式调用，this是调用方法的对象
  + 以构造函数的形式调用，this是新创建的那个对象
  + 使用call和apply调用，this是指定的那个对象



# augment：

+ 调用函数，浏览器每次都会传递进两个隐含的参数
  + 函数的上下文this
  + 封装实参的对象 arguments
    + arguments是一个**类数组**对象，它可以通过索引来操作数组，也可以获取长度
    + 调用函数，所传递的实参都会在arguments中保存
    + argument.length可以获取实参的长度
  + 有一个属性叫callee
    + 这个属性对应一个函数对象，就是当前正在指向的函数对象





# Date对象

+ Js中以Date对象来表示一个时间

+ 创建一个Date对象

```js
var d = new Date();//当前代码执行的时间
```

+ 创建一个指定时间对象，需要在构造函数中传递一个表示时间的字符串作为参数
+ 日期格式：月份/日/年 时：分：秒

```js
var d2 = new Date("12/03/2016 11:10:30")
```



getDate（）获取当前日期

getDay（）获取当前对象是周几，返回0-6值，0表示周日，以此类推

getMonth（）获取当前月份，返回0-11值，0表示一月，以此类推

getFullYear（）获取当前日期的年份

getTime（）获取当前时间戳

+ 时间戳，格林威治标准时间1970年1月1日，0时0分0秒，到当前日期所花费的毫秒数（1秒=1000毫秒）
+ 计算机底层在保存时间时使用的是时间戳

获取当前时间戳：

```js
time = Date.now();
```

可以测试程序运行时间：

```js
var start = Date.now();
...
var end = Date.now();
console.log(end-start);
```



# Math

+ Math 和其他对象不同，不是一个构造函数
+ 它属于一个工具类不用创建对象，里面封装了数学相关的属性和方法

```js
console.log(Math.abs(-1));//1 取绝对值
```



Math.ceil()

+ 向上取整，小数位只要有值就自动进1

Math.floor()

+ 向下取整，小数部分被舍掉

Math.round()

+ 四舍五入取整

Math.random()

+ 用来生成0-1之间的随机数
+ 没有0也没有1

生成0-10:乘10，取整

```js
Math.round(Math.random()*10)；
Math.round(Math.random()*9+1)；//1-10
```

生成x-y：

```js
Math.round(Math.random()*(y-x)+x);
```



max()

+ 获取多个数中的最大值

```js
var max = Math.max(10,20,30);
console.log(max);//30
```

min()

+ 获取多个数中的最小值

```js
var min = Math.min(10,20,30);
console.log(min);//30
```



pow(x,y)

+ x的y次幂



# 包装类

基本数据类型：

String Number boolean Null undefined

引用数据类型：

object



Js中有三个包装类，通过他们可以将基本数据类型转换为对象

+ String（）将基本数据类型的数字转换为String对象
+ Number（） 将基本数据类型的数字转换为Number对象
+ Boolean（）将基本数据类型的数字转换为Boolean对象



```js
var num = new Number(3);
var str = new String("hello");
var bool = new Boolean(true);

num.hello("hello");//向num中添加一个属性
console.log(num.hello);
```

