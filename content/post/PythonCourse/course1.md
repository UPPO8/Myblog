---
title: Python基础语法1
description: 
date: 2024-09-30
slug: 
image: images/PythonCourse/write-plan.jpg
categories:
    - 学习记录
    - Python
---

## 引言
Python作者：Guido von Rossum(吉多·范·罗苏姆)\
诞生时期：1991年，第一个Python解释器诞生.它是用C语言实现的，并能够调用C语言的库文件.

![](images/PythonCourse/Guido-van-Rossum.png)

编程语言的种类有很多，但目前常用的有C、C++、Java、JavaScript、C#、PHP、Ruby以及Python，并且在2021年Python已经超过C称为第一受欢迎的编程语言.

## Python的优缺点
以下代码使用C语言和Python输出a+b的例子:
```C
-----C语言中-----
#include <stdio.h>
int main()
{
    int a = 1;
    int b = 1;
    printf("%d\n",a + b);
    return 0;
}
-----Python-----
a = 1
b = 1
print(a + b)
```
这里的代码我们可以发现,Python中每行代码通常代表一条语句的结束,且不需要任何的符号作为每行的结束符.

## 缩进与注释
在Python中，通过缩进来组织代码块，例如函数体、循环体、类等.缩进必须一直，通常使用空格来实现（推荐使用4个空格），也可以使用一个制表符.并且同一级别的代码块具有相同的缩进量，下一级别的代码块应比上级别的代码
块增加一个缩进层级.例如:

```python
# 使用for和range函数生产9*9乘法表
for i in range(1,10):
    for j in range(1,i+1):
        print(f"{j} * {i} = {j*i}",end=' ')
    print()
```
这个例子中,单行注释以(#)开头,井号(#)所在位置的右边都会被当作注释.多行注释则是三引号'''或""",引号中间的内容注释掉.
```python
'''
# 求1到100的和
sum = 0
for i in range(1,101,1):
    sum += i
    print(sum)
'''
```

## 变量与关键字

变量的三个基本属性:\
  id号:反映的是变量值的内存地址.\
  类型:每一个变量都有自己的类型.\
  值:存储的数据.

```python
# 查看变量id好id()
# 查看变量类型type()
# 使用 is 或 is not 比较两个变量的id号是否相同
a = 2
b = 'nihao'
c = 2

print(id(a), id(b), id(c))
print(type(a), type(b), type(c))
print(a is b ,a is c)
```
输出结果:
```py
140719832613704 3081789329776 140719832613704
<class 'int'> <class 'str'> <class 'int'>
False True
```
输出结果中可以发现,a和c的id号与类型是一致的,使用is判断返回结果为True.

变量命名的注意事项:\
1.只能包含字母、数字、下划线，但不能以数字开头。\
2.不能包含空格，但是可以使用下划线来分割名称。\
3.不能使用Python的关键字作为标识符的名称。

## Python运算符

在Python中，常用的运算符分为以下几类：
### 算数运算符
算术运算符包括以下几种：\
  +：加法运算符，返回两个对象的和\
  -：减法运算符，返回两个对象的差\
  *：乘法运算符，返回两个对象的积\
  /：除法运算符，返回两个对象的商\
  //：整除运算符，返回两个对象的商的整数部分\
  %：取余运算符，返回两个对象的商的余数部分\
  **：平方运算符：返回两个对象的平方运算的结果
### 比较运算符
比较运算符包括以下几种：\
  ==：等于，比较两个对象是否相等，返回布尔值\
  ！=：不等于，比较两个对象是否不相等，返回布尔值\
  ＞：大于，比较两个对象的大小关系，返回布尔值\
  <：小于，比较两个对象的大小关系，返回布尔值\
  ＜=：大于等于，比较两个对象的大小关系，返回布尔值\
  <=：小于等于，比较两个对象的大小关系，返回布尔值
### 逻辑运算符
逻辑运算符
逻辑运算符包括以下几种：
  and：布尔与，and两边都为True时，才会返回True，只要有一个为False，就会返回False\
  or：布尔或，or两边都为False时，才会返回False，只要有一个为True，就会返回True\
  not：布尔非，将True改为False，将False改为True
### 赋值运算符
赋值运算符包括以下几种：
  =：赋值运算符，把=右边的对象赋值给=左边的对象\
  +=：加法赋值运算符\
  -=：减法赋值运算符\
  *=：乘法赋值运算符\
  /=：除法赋值运算符\
  //=：整除赋值运算符\
  %=：取余赋值运算符\
  **=：平方赋值运算符
### 位运算符
位运算符包括以下几种：\
  &：按位与，对两个数据的补码进行位与位之间的与运算，全1为1，有0则0\
  |：按位或，对两个数据的补码进行位与位之间的或运算，全0为0，有1则1\
 ^：按位异或，对两个数据的补码进行位与位之间的异或运算，相同为0，同为1

### 运算符的优先级
运算符的优先级（从上向下排列，上面的优先级最高）：\
圆括号()：圆括号内的表达式拥有最高优先级\
**：乘方运算\
*、/、%、//：算术运算符，先乘除\
+、-：算数运算符，后加减\
<<、>>：位运算符的左移与右移\
&：位运算符的按位与\
^：位运算符的按位异或\
|：位运算符的按位或\
＞、＜、>=、<=、==、!=：比较运算符\
and、or：逻辑运算符\
=、+=等赋值运算符优先级最低

## 输入与输出
在Python中，使用内置的print()函数进行输出，并且有几种不同的输出方式如下所示：

  ### 基本输入输出：
  使用input()输入,使用print()输出,直接打印数据或变量:
  ```py
  a = 2
  print(a)
  ```

  ### 格式化输出：
  使用百分号(%)格式符:
   格式符 | 解释
--------|------
  %c|字符
  %s |字符串
  %d |有符号十进制整数
  %f |浮点数
  %e |科学计数法
  %o |八进制整数
  
  现在不推荐使用，但是旧版本的代码中很常见.
  ```py
  a = 2
  print('%d',a)
  ```
  
  ### format()方法：
  使用花括号{}作为占位符来指定要格式化的数据类型和格式，然后通过将数据插入到占位符中来生成最后的输出结果。
  ```py
  #用format方法
  name = 'zhangsan'
  age = 18
  weight = 55.55632
  print("My name is {} and {} years old and {} weight".format(name,age,weight))
  # 控制浮点数精度 :.nf,n为位数\n",
  print("My name is {} and {} years old and {:.4f} weight".format(name,age,weight))
  ```
  ### f-string：
  在字符串前加一个f或F，然后在输出的内容中加上花括号{}，花括号{}里面是要输出的表达式，是一种新的字符串格式方法，在Python3.6版本之后引入的输出方法。
```py
  #用format方法
  name = 'zhangsan'
  age = 18
  weight = 55.55632
  print(f"My name is {name} and {age} years old and {weight} weight")
  # 控制浮点数精度 :.nf,n为位数\n",
  print(f"My name is {name} and {age} years old and {weight:.2f} weight")
  ```

## 六大基本数据类型
  数据类型 | 解释
--------|------
mymum = 11 |数值
myfloat = 3.141|浮点数
mystr = 'hello' |字符串
mylist = [1,2,3,4] |列表
mytuple = (1,2,3,4) |元组:
myset = {1,2,3,4} |集合
mydict = {"key1":"value1"} |字典

强制数据类型转换函数
  函数 | 解释
--------|------
int(x)|转换为整数
float(x)|转换为浮点数
str(x)|转换为字符串
tuple(s)|序列转换为元组
list(s)|序列转换为列表
hex(s)|序列转换为16进制

## 每日一曲

<iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width=330px height=86px src="
https://i.y.qq.com/n2/m/outchain/player/index.html?songid=509886941&songtype=0"></iframe>

