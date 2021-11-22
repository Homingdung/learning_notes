C++ 笔记

# 第一部分 C++ 基础

## 注释

```c++
// 单行注释
/*多行注释*/
/*main 是一个程序的入口，每个程序必须有这么一个函数，有且只有一个*/
```

## 变量

作用：给一段指定的内存空间起名，方便操作这段内存

意义：方便管理内存空间

```c++
int main(){
  int a = 10;
  cout << "a = " << a << end1;
  system("pause");
  return 0;
}
```



## 常量 

作用：记录不可更改的数据

1. #define 宏常量：通常定义在文件的上方
2. const修饰变量：通常在变量定义前加关键词 const

```c++
//1 宏常量
#define day 7
int main(){
  cout<< "一周里总共有"<<day<<"天"<<end1;
  //day = 8;//报错，宏常量不可以修改
  
  //2.const修饰变量
  const int month = 12; // const 修饰的变量也称为常量
  cout<<"一年里总共有"<<month<<"个月份"<<end1;
  //month = 24;//报错，常量不可以修改
  
  system("pause");
  return 0;
}
```



## 关键字

作用：预先保留的单词（标识符）

+ 定义变量或常量的时候，不要用关键字

## 标识符命名规则

+ 不可以是关键字
+ 只能由字母，数字，下划线组成
+ 第一个字符必须为字母或下划线
+ 字母区分大小写

建议：见名知义

## 数据类型

c++创建一个变量或常量，必须指定相应类型，**不然无法分配内存**

### 整型

c++整型有：short,int,long,long long，区别在于所占内存空间不同

```c++
int main(){
  short num1 = 10;
  int num2 = 10;
  long num3 = 10;
  long long num4 = 10;
}
```

## sizeof 关键字

作用：利用sizeof关键字统计数据类型所占内存大小

```c++
int main(){
  short num1 = 10;
  cout <<"占用内存"<< sizeof(short)<<end1;
  system("pause");
  
}

```

## 实型（浮点型）

1. 单精度float
2. 双精度double

两者区别在于有效数字范围不一样

```c++
int main(){
  float f1 = 3.14f;
  double d1 = 3.1415926;
  float f2 = 3e2;//10^2
  system("pause");
  return 0
}
```

默认情况下，输出一个小数，会显示出6位有效数字

## 字符型

作用：表示单个字符

语法：```char ch = 'a';```

> 注意1：显示字符型变量时，用单引号，不要用双引号
>
> 注意2：单引号内只能有一个字符，不可一世字符串

+ C和Cpp字符型变量只占用一个字节
+ 字符型变量并不是把字符本身放到内存中，而是将对应的ASCII编码放到储存单元中

```cpp
int main(){
  //1.字符型变量创建的方式
  char ch = 'a';
  cout << ch << endl;
  //2.字符型变量所占内存大小
  cout << "占用内存" << sizeof(char) << endl;
  //3.常见错误
  //char ch2 = "b"
  //char ch2 = 'abcdef' 
  //4.对应ASCII编码
  cout << (int)ch << endl;
}
```

## 转义字符

作用：用于表示一些不能显示出来的ASCII字符

\n: 换行



```cpp
int main(){
  //换行符 \n
  cout << "hello world"<< endl;
  cout << "hellow world \n";
    
  //反斜杠 \\
  cout << "\\" << endl;
  
  //水平制表符 \t 输出对齐功能
  cout << "aaa\thelloworld"<< endl;
}
```



## 字符串型

作用：用于表示一串字符

1. C风格字符串：```char 变量名[ ] = “字符串值”```
2. C++ 风格字符串：```string 变量名 = "字符串值“```

```cpp
#include <string> // 用C++风格 包含头文件
int main(){
  // C风格
  char str[] = "hello world";
  cout << str<< end1;
  //注意事项 1. char 字符串名 [] 2. 等号后面要用双引号包含字符串
  // C++风格
  string str2 = "hello world";
  cout << str2 << endl;
}
```



 

## 布尔类型 bool

作用：真假

+ true
+ false

bool类型占用一个字节

```cpp
int main(){
  // 创建bool数据类型
  bool flag = true;
  cout<<flag<<endl;
  flag = false;
  // 查看所占内存空间
  cout<<"bool 所占空间"<<sizeof(bool)<endl;
}
```

## 数据的输入

作用：用于从键盘获取数据

关键字：cin

语法：```cin >> 变量```

```cpp
int main(){
  //1.整型
  int a = 0;
  cout << "请给变量赋值："<< endl;
  cin >> a;
  cout << "整型变量 a = " << a << endl;
  //2.浮点型
  float f = 3.14f;
  cout << "请赋值："<< endl;
  cin >> f;
  //3. 字符型
  char ch = 'a';
  cout<< "请赋值" << endl;
  cin >> ch;
  cout<<"a = "<< ch << endl;
  //4. 字符串型
  string str = "hello";
  cout<<"请给字符串 str赋值"<< endl;
  cin >> str;
  cout<< "字符串str ="<< str <<endl;
  //5.布尔值
  bool flag = false;
  cout<<"please:"<<endl;
  cin >> flag;
  cout<<"output"<<flag<<endl;
  
  
  
    
}
```

非零都是true

## 运算符

1. 算术运算符
2. 赋值运算符
3. 比较运算符
4. 逻辑运算符

```cpp
int main(){
  //加减乘除
  int a1 = 10;
  int b1 = 3;
  cout<<a1+b1<<endl;
  cout<<a1-b1<<endl;
  cout<<a1*b1<<endl; 
  cout<<a1/b1<<endl; // 两个整数相除，结果依然是整数，将小数部分去除
  double d1 = 0.5;
  double d2 = 0.25;
  cout<<d1/d2<<endl;
} 
```

取模：%（取余数） 10 % 3 = 1

两个小数不可以作取模运算；

递增运算： ++

递减运算：--

```cpp
int main(){
  int a = 10;
  ++a; //让变量加1
  int b = 10;
  b++;//让变量加1
  int a2 = 10;
  int b2 = ++a2 * 10;
  int a3 = 10;
  int b3 = a3++ * 10;
}
```

前置递增，先加1然后运算

后置递增，先运算后加1

## 赋值运算符

=, +=, -=, *=, /=, %=

```cpp
int main(){
  int a = 10;
  //=
  a = 100;
  //+=
  a = 10;
  a+=2;
  //-=
  a = 10;
  a-=2;
  //*=
  a = 10;
  a*=2;
  ///=
  a = 10;
  a/=2;
  //%=
  a = 10;
  a%=2;
  
}
```

## 比较运算符

==, !=, <, >, <=, >=

## 逻辑运算符

!非, &&与, || 或

```cpp
int main(){
  int a = 10;
  cout<<!a<<endl;//除了0都是真
  
}
```



## 程序流程结构

顺序结构，选择结构，循环结构

+ 顺序结构：按顺序执行
+ 选择结构：依据条件是否满足，有选择的执行
+ 循环结构：依据条件是否满足，循环多次某段代码



if 语句：

if 后面不加分号，加分号条件白写

+ 单行格式
+ 多行格式
+ 多条件格式





```cpp
int main(){
  //单行if
  int score =0;
  cout<<"plz input score"<<endl;
  cin >> score;
  cout<<"output:"<<score<<endl;
  if (score > 650)
  {
    cout<<"congra!"<<endl;
  }
  //多行if
  int score = 0;
  cout<<"plz input:"<<endl;
  cin>>score;
  
  if (score >600)
  {
    cout<< "congrat!"<<endl;
  }
  else
  {
    cout<<"so sad"<<endl;
  }
  //多条件
  if (score>600)
  {
    ...
  }
  else if
  {
    ...
  }
  else if
  {
    ...
  }
}


```

嵌套if

```cpp
int main(){
  int score = 0;
  cout<<"plz input:"<<endl;
  cin>>score;
  if (score >600)
  {
    ...
      if (score >700)
      {
        ...
      }
    else if (score >650)
    {
      ...
    }
    else
    {
      ...
    }
  }
  else if (score >500)
  {
    ...
  }
  else if (score >400)
  {
    ...
  }
  else
  {
    ...
  }
}
```

## 三目运算符

作用：简单判断

语法：表达式1？表达式2？表达式3



```cpp
int main(){
  int a = 10;
  int b = 20;
  int c = 0;
  c = (a>b ? a : b);
  cout<<"c="<<endl;
  
  //三目运算符返回的是变量，可以继续赋值
  (a > b ? a : b)=100;
  
  
  return 0
}
```

## Switch 语句

作用：执行多条件分支语句

```cpp
switch(表达式)
{
  case1；
  case2;
  ...
  default
}
```



```cpp
int main(){
  cout<<"plz input score:"<<endl;
  int score = 0;
  cin >> score;
  switch (score)
  {
    case 10:
      cout<<"classical movie"<<endl;
      break;
    case 9:
      
  }
  
  
  return 0
}
```

switch 缺点：判断时候只能是整型或者字符型，不可是一个区间

switch 优点：结构清晰，执行效率高

## 循环结构

### while循环结构

作用：满足循环条件，执行循环语句

```cpp
int main(){
  int num = 0;
  cout<<num<<endl;
  while (num <10){
    num ++;
    cout<<num<<endl;
  }
}

```

注意：写循环，注-意死循环出现



随机数：

```cpp
#include<ctime>
int main(){
  //添加随机数种子，防止每次随机数都一样
  srand((unsigned int)time(NULL));
  int num = rand() % 100 + 1;
}
```

### do  while语句

```cpp
int main(){
  do {
    
  }
  while ();
  return 0;
}
```

先执行，再判断条件

案例：

水仙花数：一个三位数，每个位上的数字的3次幂之和等于它本身

例如：1^ 3+5^3 +3^ 3=153

利用 do while ,求所有三位数的水仙花数

1. 将所有三位数输出（100 - 999）
2. 在所有的三位数中找到水仙花数
3. 获取个位，十位，百位
   1. 个位： 153 %10 = 3
   2. 十位：153/10=15， 15%10=5
   3. 百位：153/100=1
4. 判断 个位， 十位， 百位



```cpp
#include <iostream>
int main() {
    // insert code here...
    int num = 100;
    do {
        int a = num % 10;
        int b = num / 10 % 10;
        int c = num / 100;
        
        if (a*a*a + b*b*b + c*c*c == num)
        {
            std::cout<<num<<std::endl;
        }
        num ++;
    }
    while(num < 1000);
    
    
    return 0;
}
```



### for 循环

```cpp
int main(){
  for (i = 0;i < 10; i++){
    
  }
}
```

for循环中表达式，要用分号进行分隔

for循环结构清晰



## 嵌套循环

```cpp
#include <iostream>
int main() {
    // insert code here...
    for (int i = 0; i<10;i++){
        for (int j = 0; j<10;j++){
            std::cout<<"*"<<"";
            
        }
        std::cout<< std::endl;
    }
}

```

乘法口诀表：

列数x行数 = 结果

列数< = 当前行数

```cpp
#include <iostream>
int main() {
    // insert code here...
    for (int i = 1; i <= 9; i++){
        for (int j = 1;j <= i ; j++){
            std::cout<<j<<"*"<<i<<"="<<i*j<<" ";
        }
        std::cout<<std::endl;   
    }
}
```

## 跳转语句

### break 语句

+ 出现在switch语句，终止case跳出switch
+ 出现在循环语句，跳出当前循环语句
+ 出现在嵌套语句，跳出最近循环



### continue 语句

作用：跳过本次循环余下尚未执行的语句，继续执行下一次循环

### goto 语句

作用：无条件跳转语句

```cpp
int main(){
  cout<<"1"<,endl;
  cout<<"2"<,endl;
  goto FLAG;
  cout<<"3"<,endl;
  cout<<"4"<,endl;
  FLAG:
  cout<<"5"<<endl;
  
}
```

## 数组

数组：一个集合，里面存放了相同类型的数据元素

+ 每一个数据元素都是相同的数据类型
+ 数组是连续内存位置组成的

### 一维数组

三种定义方式：

+ ```数据类型 数组名 [数组长度]```

+ ```数据类型 数组名[数组长度] = {值1，值2，值3}```
+ ```数据类型 数组名[]={值1，值2...}```

```cpp
int main(){
  // 数据类型 数组名 [长度]
  int arr[5];
  arr[0] = 10;
  arr[1] = 20;
  arr[2] = 30;
  arr[3] = 40;
  arr[4] = 50;
  //访问数据元素
  cout<<"arr[0]"<<endl;
  // 数据类型 数组名[长度] = {值1，值2...}
  int arr2[5] = {10,20,30,40,50};
  // 数据类型 数组名[] = {值1，值2...}
  //必须有初始长度
  int arr3[] = {90,80,70};
}
```

#### 一维数组组名

用途：

+ 统计整个数组在内存中的长度 ```sizeof(arr)```
+ 获取数组在内存中的首地址 ```cout<<arr<<endl;```

 

