---
title: Python基础语法3
description: 
date: 2024-10-01
slug: 
image: images/PythonCourse/R-C.png
categories:
    - 学习记录
    - Python
---
## 数据类型-数字
在Python中,数字类型包括以下几种:

1.整型int( ):包括正整数,负整数和0,在程序中的表达与数学上一致

2.浮点型float( ):小数.

3.布尔型bool( ):特殊的整型,只用True和False,True为1,False为0.

4.复数complex( ):与数学上表达式一致,分为实部与虚部,用j表示,多用于科学计算.

### 布尔型数据的短路求值
在Python中,布尔型数据的短路求值是一种特殊的逻辑运算规则，当逻辑表达式的某个部分已经能够确定整个表达式的值时，就不再计算表达式的其余部分。
比如在下面个例子中
```py
a = 10
b = 0
re1 = a or b
re2 = a and b
print(re1,re2)
```


## 数据类型-字符串
字符串由引号括起来的一系列数字,字母,及中文的组合,并且定义好的字符串是不可修改的.
```py
#单引号
src = 'hello world'
#三引号创建多行字符串
src2 = '''
闲吟秋景外，
万事觉悠悠。
此夜若无月，
一年虚过秋。
'''
print(src1)
print(src2)
```

### 转义字符
转义字符：是一种特殊字符，用于表示无法直接表示的字符，以反斜杠“\”开头。\
常用的转义字符：

    换行符：\n，用于实现换行。
    制表符：\t，相当于一个Tab。
    回车符：\r，将光标移至当前行的开头。
    反斜杠：\\，将反斜杠本身转义，使反斜杠本身成为一个普通字符。
    单引号与双引号：\’和\”，将单引号与双引号转义，使其不再是字符串的标识，而是仅仅只是一个单引号或双引号。

### 字符串的访问
字符串的访问有下标访问与切片访问。下标访问：所谓的下标，其实就是编号，通过编号就可以找到对应的字符，下标可按照从左至右的顺序开始计算，也可以按照从右至左的顺序开始计算，但是访问的时候下标不能超出范围。

        src = 'zhangsan'
        src[0] = z
        src[1] = h

切片访问与下标访问类似，都是通过字符串的下标进行的，不同的是，下标访问每次只能访问到单个字符，切片访问可以一次访问到多个字符，其访问方式为：

        字符串名[初始位置：终止位置：步长]

访问时，包括初始位置不包括终止位置，且步长默认为1。如果没有给出初始位置，默认初始位置为开始位置；如果没有给出终止位置，默认终止位置为字符串结束位置，此时访问时包括终止位置。

        src = 'zhangsan lisi'
        print(src[0:10:1]) 
        #打印结果:zhangsan l
        #从左0开始,到第9个,步长为1,打印输出
     
### 字符串的操作
字符串的操作总结来说有:查询、转换、判断、分割等

查询函数|解释
-------|-------
find()|检测字符串是否包含指定字符，如果是则返回开始的索引值，否则返回-1
index()|检测字符串是否包含指定字符，如果是则返回开始的索引值，否则报错
rfind()|从右向左，检测字符串是否包含指定字符，如果是则返回开始的索引值，否则返回-1
rindex()|从右向左，检测字符串是否包含指定字符，如果是则返回开始的索引值，否则报错


转换函数|解释
---|---
lower()|将字符串转换为小写
upper()|将字符串转换为大写
title()|将字符串中每个单词的首字母大写


判断函数|解释
----|----
startswith()|如果字符串一obj开头,返回True,否则返回False
endswith()|如果字符串以obj结尾，则返回True，否则返回False
isspace()|如果字符串只包含空格则返回True，否则返回False
isalnum()|如果字符串都是字母或数字则返回True，否则返回False
isdigit()|如果字符串都是数字则返回True，否则返回False
isalpha()|如果字符串都是字母则返回True，否则返回False


分割函数|解释
----|----
partition()|将字符串根据参数分割为三部分
rpartition()|从右向左，将字符串根据参数分割为三部分
split()|将字符串根据参数进行分割，且可以指定分割的次数
splitlines()|按照\n分割，返回一个列表


```py
#字符串的分割
#partition()函数:将字符串按参数分割
str3 = 'hello world hello python'
print(str3.partition('world'))
print(str3.rpartition('world'))

#split()将字符串分割有限次
print(str3.split(' ',2))
print(str3.splitlines())

#count()函数
print(str3.count('o'))
#join函数
str4 = '_'
str5 = ['hello','world']
print(str4.join(str5))

#replace函数
print(str3.replace('hello','nihao'))
#capitalize函数,将首字母大写
print(str3.capitalize())

```

## 每日一曲
<iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width=330px height=86px src="
https://i.y.qq.com/n2/m/outchain/player/index.html?songid=521726934&songtype=0"></iframe>
