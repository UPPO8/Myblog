---
title: Python基础语法2
description: 
date: 2024-10-01
slug: 
image: images/PythonCourse/R-C.png
categories:
    - 学习记录
    - Python
---

## 强制数据类型转换
type()函数可以用来查看一个变量的数据类型.目前常见的数据类型用下面几种:
数据类型|解释
----|----
int|整数
float|浮点数
bool|布尔值
str|字符串
list|列表
tuple|元组
set|集合
dict|字典

如果我们想转换数据类型,有两种方式.

1.显式类型转换\
显式类型转换是强制类型转换,这种转换并不是所有对象都可以安全的转换为任意其他类型,转换的过程中可能会报错.\
2.隐式类型转换\
隐式类型转换则是解释器自动将一种数据类型的值转换为另一种数据类型.\
下面举个例子
```py
a = input('输入整数a:')
b = input('输入整数b:')
print(a+b)
print(type(a))
'''
打印结果:
a:5
b:6
56
<class 'str'>
'''
```
可以看到这里打印的a+b是56,使用type函数发现输入的值以字符串形式存储的,这显然不和要求,因此需要进行输入数据转换
```py
a = int(input('输入整数a:'))
#或者
a = input('输入整数a:')
a = int(a)
```

## 条件语句
条件语句,也叫做判断语句,简单来说就是如果满足某个条件,就去做某件事,不满足就不做.

条件语句使用if关键字作判断,使用方式三种判断格式:

### if格式
这是一种基础格式,他的执行逻辑:先执行表达式,如果表达式为真,则执行代码块,否则不会执行.
```py
a = int(input('输入整数a:'))
b = int(input('输入整数b:'))
if a < b:
    print("a小于b")

```

### if-else格式
if-else执行逻辑:先执行表达式,如果表达式为真,则执行代码块1,否则执行代码块2.
```py
a = int(input('输入整数a:'))
b = int(input('输入整数b:'))
if a < b:
    print("a小于b")
else: 
    print("a大于等于b")

```

### if-elif-else
if-elif-else的执行逻辑:先执行表达式1，如果表达式1为真则执行代码块1，否则继续执行表达式2；如果表达式2为真则执行代码块2，否则继续向下执行；如果所有的表达式都为假，则 执行else分支。
```py
a = int(input('输入整数a:'))
b = int(input('输入整数b:'))
if a < b:
    print("a小于b")
elif a == b: 
    print("a等于b")
else:
    print("a大于b")

```

### match-case
在Python3.10版本后,新增加了match case语句,也可以用来作条件判断,处理复杂的条件分支:
```py
match subject:
    case condition1:
        pass#代码块1
    case condition2:
        pass#代码块2
    case _:
        pass#代码块3
    
```

## 循环语句

在Python中,循环语句是程序重复执行一段代码知道满足特定条件为止的关键结构,共有2种格式:for 和 while 两种.

### while循环
while循环语法: 如果满足条件,则进入while循环执行代码块,执行完后返回条件再判断返回结果,直到条件不满足,退出循环.

如下面求1~100累加和的例子
```py
i = 0
sum = 0
while i <= 100:
    sum += i
    i += 1
print(f"1+2+3+...+100的和为:{sum}")
```

### for循环
for循环可以循环遍历任何序列,比如字符串,列表等可遍历对象,只要可遍历
对象没有遍历完,那么代码块就会一直执行,直到可遍历对象遍历完毕.
```py
for 临时变量 in 可遍历对象:
    代码块
```
这里的可遍历对象可以是整数序列,整数列表等,也可以直接用range()函数,直接生成一个整数序列对象.
```py
range(start,stop,step)
```
从语法上可知,这个整数序列从start开始(不写默认为0);到stop结束,但是不包括stop;step为步长(不写默认为1).如range(2,9,1):返回序列[2,3,4,5,6,7,8]

```python
# 使用for和range函数生产9*9乘法表
for i in range(1,10):
    for j in range(1,i+1):
        print(f"{j} * {i} = {j*i}",end=' ')
    print()
```
### 循环控制关键字
在for和while循环中,有三种循环控制关键字.\
1.break:在代码块执行过程中终止循环,并跳出本层循环.\
2.continue:在代码块执行过程中终止本次循环，执行下一次循环.\
3.pass:空语句，相当于一个占位符，它的作用是在语法上需要一个语句，但
程序不需要任何操作时使用。例如,某个语句后面不写内容会报错,就会先用pass占位.

## 每日一曲
<iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width=330px height=86px src="
https://i.y.qq.com/n2/m/outchain/player/index.html?songid=509883527&songtype=0"></iframe>