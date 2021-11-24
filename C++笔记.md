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

 ```cpp
 int main(){
   //内存长度
   int arr[10] = {1,2,3,4,5,6,7,8,9,10};
   cout<<sizeof(arr)<<endl;
   cout<<arr<<endl;  
   //数组中元素的个数
   cout<<:数组中元素的个数:<<sizeof(arr)/sizeof(arr[0])<<endl;
   //首地址
   cout<<"数组首地址为"<<arr<<endl;
   cout<<"数组第一个元素的地址为"<< (long long)&arr[0]<<endl; //十进制 long long &arr[0]
   //数组名是常量，不可以进行复赋值操作
   arr = 100;
 }
 ```



案例：五只小猪称体重

```int arr[5]={300,350,200,400,250}```

找出并打印最重的小猪体重

```cpp
int main(){
  int arr[5] = {300,350,200,400,250};
  int max = 0;
  for (int i = 0;i<5;i++){
    if (arr[i] > max){
      max = arr[i];//update our maximum
    }
  }
  cout<<max<<endl;
}
```

案例：数组逆置

如 {1,3,2,5,4}, 逆置：{4,5,2,3,1}

```int star = 0``` 起始元素下标

```int end = sizeof (arr)/sizeof(arr[0])-1``` 末尾元素下标

 ```cpp
 int main(){
   //创建数组
   int arr[5] = {1,3,2,5,4};
   for(int i = 0;i<5;i++){
     cout<<arr[i]<<endl;    
   }
   //逆置
   while(start < end){
     int start = 0;
     int end = sizeof(arr)/sizeof(arr[0])-1;
     int temp = arr[start];
     arr[start] = arr[end];
     arr[end] = temp;
     start ++;
     end --;
     
   }
   
   //ouput
   for(int i = 0;i<5;i++){
     cout<<arr[i]<<endl;    
   }  
 }
 ```

### 冒泡排序

作用：组内数据排序

1. 比较相邻的元素，如果第一个比第二个大，交换
2. 对每一对相邻元素做同样的工作，执行完毕后，找到一个最大值
3. 重复以上步骤，每次比较次数-1，直到不需要比较

排序总轮数 = 元素个数-1

每轮对比次数 = 元素个数 - 排序轮数-1；

```cpp
#include <iostream>
int main() {
    // insert code here...
    int arr[9] = {4,2,8,0,5,7,1,3,9};
    for (int i = 0;i<9-1;i++){
        for (int j = 0;j < 9-i-1;j++){
            if (arr[j] > arr[j+1]){
                int temp = arr[j];
                arr[j] = arr[j+1];
                arr[j+1] = temp;
            }
        }
    }
    
    for (int k = 0; k < 9;k++){
        
        std::cout<<arr[k]<<std::endl;
        
    }
}
```

## 二维数组

定义方式：

1. ```数据类型 数组名[行数][列数];```
2. ```数据类型 数组名[行数][列数] = {{数据1，数据2},{数据3，数据4}};```
3. ```数据类型 数组名[行数][列数] = {数据1，数据2，数据3，数据4};```
4. ```数据类型 数组名 [][列数] = {数据1，数据2，数据3，数据4}；```

第二种更加直观，提高代码的可读性

```cpp
int main(){
  //1.
  int arr[2][3];
  arr[0][0] = 1;
  arr[0][1] = 2;
  arr[0][2] = 3;
  arr[1][0] = 4;
  arr[1][1] = 5;
  arr[1][2] = 6;
  for (int i = 0; i <2;i++){
    for (int j = 0;j < 3;j++){
      cout<<arr[i][j]<<endl;
    }
  }
  //2.
  int arr[2][3] = 
  {
    {1,2,3},
    {4,5,6}
  };
  for (int i = 0;i < 2;i++){
    for (int j = 0;j<3;j++){
      cout<<arr[i][j]<<"";
      
    }
    cout<<endl;
  }
  //3.
  int arr[2][3] = {1,2,3,4,5,6};
  for (int i = 0;i < 2;i++){
    for (int j = 0;j<3;j++){
      cout<<arr[i][j]<<"";
      
    }
    cout<<endl;
  }
  //4.
  int arr[][3] = {1,2,3,4,5,6};  
}
```

#### 二维数组组名

+ 查看二维数组所占内存空间
+ 获取二维数组首地址

```cpp
int main(){
  //1. 可以查看占用内存空间大小
  int arr[2][3] = 
  {
    {1,2,3},
    {4,5,6}
  };
  cout<<"二维数组占用空间："<<sizeof(arr)<,endl;
  cout<<"二维数组第一行占用的内存空间"<<sizeof(arr[0])<<endl;
  cout<<"二维数组第一个元素占用的内存为："<<sizeof(arr[0][0])<<endl;
  cout<<"二维数组的行数为："<<sizeof(arr)/sizeof(arr[0])<<endl;
  cout<<"二维数组的列数为"<<sizeof(arr[0])/sizeof(arr[0][0])<<endl;
  //2. 查看二维数组的首地址
  cout<<"二维数组的首地址："<<(long long)arr<<endl; // (long long)转十进制
  cout<<"二维数组第一行首地址："<<(long long)arr[0]<<endl;
  cout<<"二维数组第二行首地址:"<<(long long)arr[1]<<endl;
  
  cout<<"二维数组第一个元素首地址："<<(int)&arr[0][0]<<endl;
  cout<<"二维数组第二个元素首地址："<<(int)&arr[0][1]<<endl; 
}
```

## 函数

作用：将一段代码封装起来

定义：

1. 返回值类型
2. 函数名
3. 参数表列
4. 函数体语句
5. return 表达式

```cpp
int main(){
  int add(int num1, int num2){
    // num1 num2 叫形参，真实数据叫实参
    int sum = num1 + num2;
    return sum;
  }
}
```

## 函数调用

功能：使用定义好的函数

语法：```函数名```

```cpp
#include <iostream>
int add(int num1, int num2){
    int sum = num1 + num2;
    return sum;
}


int main() {
    // insert code here...
    int a = 2;
    int b = 2;
    int c = add(a,b);
    std::cout<<c<<std::endl;
}

```

## 值传递

+ 值传递：函数调用时将实参传入给形参
+ 值传递时，如果形参发生变化，并不会影响实参

```cpp
//定义一个函数
//如果函数不需要返回值，声明的时候可以写一个void
void swap(int num1, int num2){
  int temp = 0;
  num1 = num2;
  num2 = temp;
  return;//返回值不需要的时候可以不写return
  cout<<num1<<endl;
  cout<<num2<<endl;
}
int main(){
  int a = 10;
  int b = 20;
  swap(a,b);
}
```

## 函数常见样式

常见样式有四种：

1. 无参无返
2. 有参无返
3. 无参有返
4. 有参有返

```cpp
//1. 无参无返
void test01(){
  cout<<"this is test01"<<endl;
}
//2. 有参无返
void test02(a){
  cout<<"this is test02"<<a<endl;
}
//3. 无参有返
int test03(){
  cout<<"this is test03"<<endl;
  return 1000
  
}
//4. 有参有返
int test04(){
  cout<<"this is test 04"<<a<<endl;
  return 1000;
}
//调用
int main(){
  //1. 无参无返
  test01();
  //2. 有参无返
  test02(100);
  //3. 无参有返
  int num1 = test03();
  cout<<"num1"<<num1<<endl;
  //4. 有参有返
  int num2 = test04(10000);
  cout<<"num2="<<num2<endl;
}
```

## 函数声明

作用L：告诉编译器函数名称如何调用，函数的实际主题可以单独定义

+ 函数的声明可以多次定义，但是函数的定义只能有一次

```cpp
int max(int a, int b){
  return a>b?a:b;
}
int main(){
  int a = 10;
  int b = 20;
  cout<<max(a,b)<<endl;
}

//提前告诉编译器函数的存在，可以利用函数声明
//声明
int max(int a, int b);
//调用
int main(){  
  int a = 10;  
  int b = 20;  
  cout<<max(a,b)<<endl;
}
//定义
int max(int a, int b){  
  return a>b?a:b;
}

```

## 函数的份文件编写

作用：让代码结构更加清晰

函数分文件写的一般有四个步骤：

1. 创建后缀名为.h的头文件
2. 创建后缀名为.cpp的头文件
3. 在头文件中写函数的声明
4. 在原文件中写函数的定义

 ```cpp
 #include <iostream>
 using namespace std;
 #include "swap.h"
 //函数分文件编写
 //实现两个数字进行交换的函数
 
 //函数的声明
 void swap(int a, int b);
 void swap(int a, int b){
   int temp = a;
   a = b;
   b = temp;
   cout<<a<<endl;
   cout<<b<<endl;
 }
 int main(){
   int a = 10;
   int b = 20;
   swap(a,b);
 }
 
 //1. 创建.h后缀名的头文件
 //2. 创建.cpp后缀名的源文件
 //3. 在头文件中写函数的声明
 //4. 源文件中写函数的定义
 ```

## 指针

作用：可以通过指针间接访问内存

+ 内存编号从0开始记录的，一般用十六进制数字表示
+ 可以利用指针变量保存地址
+ 指针就是一个地址

定义 ```数据类型 * 变量名```

```cpp
int main(){
  //1. 定义一个指针
  int a = 10;
  //指针定义的语法: 数据类型 * 指针变量名;
  int * p;
  //让指针记录变量a的地址（建立关系）
  p = &a; //&取地址符号
  cout<<"a的地址为："<<&a<<endl;
  cout<<"指针p为："<<p<<endl;
  //2. 如何使用指针
  //可以通过解引用的方式来找到指针指向的内存
  //指针前加 * 代表解引用，找到指针指向的内存中的数据
  *p = 1000;
  cout<<"a="<<a<endl;
  cout<<"*p="<<*p<<endl;
}
```

### 指针占用内存空间

提问：指针也是种数据类型，这种数据类型占用多少内存空间呢

+ 32位操作系统下， 指针是占4个字节空间大小，不管是什么类型
+ 64位操作系统下，指针是占8个字节空间大小，不管是什么类型

```cpp
int main(){
  //指针所占内存空间
  int a = 10;
  //int *p;
  //p = &a;
  int *p=&a;
  cout<<"sizeof int * ="<<sizeof(int *)<<endl;
}
```



### 空指针和野指针

空指针：指针变量指向内存中编号为0的空间

用途：初始化指针变量

注意：空指针指向的内存是不可以访问的

```cpp
int main(){
  //1.空指针用于给指针变量进行初始化
  int * p = NULL;
  
  //2.空指针式不可以进行访问的
  //0-255之间的内存编号是系统占用的，因此不可以访问
  cout<<*p<<endl; //报错
  
}
```

  

野指针：指针变量指向非法的内存空间

```cpp
int main(){
  int *p = (int *)0x1100;
  cout<<*p<<endl;
}
```

总结：空指针和野指针都不是我们申请的空间，因此不要访问

## const修饰指针

三种情况：

1. const修饰指针--常量指针
2. const修饰常量 --指针常量
3. const即修饰指针，又修饰常量

 
