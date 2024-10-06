---
title: Python基础语法4
description: 
date: 2024-10-02
slug: 
image: images/PythonCourse/R-C.png
categories:
    - 学习记录
    - Python
---
## 数据类型-列表

列表：是一种有序的元素集合，用于存储一组有序的数据，可以包含任意数量的元素，并且每个元素可以是不同的数据类型。与字符串不同的是，列表里的元素是可以修改的。

其表示方法为:

        列表名称 = [元素1,元素2,....,元素n]

列表的访问方式有下标访问和切片访问.列表的下标访问和切片访问与字符串的索引一样.

不同的是,列表的切片访问可以访问多个元素

## 列表的操作
对列表中内容,主要有增加,删除,修改,查找.
### 列表的内容增加:
        append()像列表尾部加入元素;
        insert()在列表指定位置加入袁术;
        extend()将一个列表的所有元素添加到另一个列表

```py
###append()用法###
list1 = [1,2,3]
list1.append(4)
print(list1)
###insert()用法###
list2 = [1,2,3]
list2.insert(2,4)#在下标2处插入4
print(list2)
###extend()用法###
list1 = [1,2,3]
list1.extend([4,5,6])
print(list1)
```

### 列表的内容删除:
        remove(元素)删除指定元素,列表中必须包含该元素
        pop(下标)移除列表的一个元素,并返回该元素,
        clear()删除列表中的所有元素
        del  关键字,指定下标时删除对应元素,未指定则删除整个列表对象

```py
ls = [1,2,3]
#remove删除列表中的'1'
print(ls.remove(1))
#打印结果:[2,3]

#pop将指定下标的元素取出
print(ls.pop(1))
##打印结果:2

#clear函数
print(ls.clear())
#打印结果:[]

#del是一个关键字,当指定下标时,删除指定元素
del ls[0]
del ls
#不指定下标时,为删除这个列表吗,后续不可再用
```

### 列表的内容修改:
    修改格式    
        列表名[索引] = '新内容'
```py
list1 = [1,2,3,4]
list1[0] = 0
print(list1)
```

### 列表的内容查找:
        1.count()返回列表中某个元素的数量
        2.使用in关键字查找,如果存在就返回True,否则返回False

```py
#count使用
ls = [1,2,3,4,5]
print(ls.count(3))
#打印结果:1

#使用in关键字
if 1 in ls:
    print('1在列表中')
```

### 列表的其他常用操作:
        len()获取列表中元素的个数
        reverse()反转列表中的元素
        sort()对列表元素进行排序(只针对数字型列表)
        copy()对列表的拷贝
        ls[][]列表的嵌套,如ls[[1,2],[3,4]]

```py
#对数字列表排序
list1 = [1,88,36,45,42,9]
list1.sort(reverse=True)#默认False从小到大排序
print(list1)
#如果想对字符串排序
list1 = ['a','bdf','de','dasdd']
list1.sort(reverse=True,key=len)#依据字符串的长度排序
print(list1)
#列表的浅拷贝,
l1 = [1,2,3]
l2 = l1.copy()
#列表的深拷贝
import copy
l3 = copy.deepcopy(l1)
#列表推导式,如对列表平方
ls = [1,2,3,4,5]
squared_ls = [x ** 2 for x in l1]
print(squared_ls)
```

## 数据类型-元组
元组:与列表相似,不同之处在于元组的元素不可修改.\
元组的表示使用()表示:

        元组名 = (元素1,元素2,...,元素n)

元组元素的访问,有下标与切片访问,与字符串、列表的方式相同.

### 元组的常用操作
元组的常用操作:
        len():获取元组中元素的个数
        max():返回元组中元素最大值
        min():返回元组中元素最小值
        使用in或not in 查找元素是否在元组中
        del:删除元组,使用和列表相同

元组的推导式语法:

        for 元素 in 元组 if 条件1

## 序列
元组、列表、字符串的共同点:

    1.都可以通过下标获取每一个元素.
    2.第一个元素的下标为0(从左到右).
    3.都可以通过切片的方法获取一个范围.

这些共同点简称序列.其中列表是可变序列,元组和字符串是不可变序列. 

### 序列的操作
 min()和max(),可以用于统计序列中最大值和最小值,根据传入的序列和参数的不同有不同的结果.



len()函数:用来计算序列的长度或元素的个数.

sum()函数:求序列元素的和,可以通过start参数来决定求的初始值.
```py
s1 = [1,2,3,4,5]
print(sum(s1,start=10))
```
sorted():用于对序列进行排序,与列表的sort函数不同在于,该函数会返回一个全新的列表,原有的序列不会改变.
```py
s = [1,2,3,4,6]
print(sorted(s,reverse=True))
s.sort()
print(s)
```
reversed():对序列进行反转,该函数会返回一个迭代器,需要通过强转或for循环来观看元素
```py
s = [1,2,3,4,5,6]
for i in reversed(s1):
    print(i)
```
all():用于判断序列中的所有元素是否为真,返回布尔值.\
any():用于判断序列中的某个元素是否为真,返回布尔值.
```py
s = [1,2,3,4,5,6]
print(all(s))
print(any(s))
```
enumerate():用于将一个可遍历对象的数据对象中的下标与元素组合起来,返回的是枚举对象(类似:(0,'H'))
```py
s = ['a','b','c','d','e']
for i in enumerate(s):
    print(i)
```

zip():用于将多个可迭代对象中对应位置的元素打包成一个元组,然后返回这一元组.
```py
l1 = [1,2,3]
l2 = [4,5,6]
l3 = [7,8,9]
l4 = zip(l1,l2)
print(list(l4))
l5 = zip(l1,l2,l3)
print(list(l5))
```

此外还有map()函数:对可迭代对象中的每个元素用一个指定的函数;filter()函数:对可迭代对象中的每个元素用一个指定的函数,并返回结果为真的元素.

## 数据类型-集合
集合是一个无序的不重复的序列,分为可变和不可变集合.\
可变集合的元素在定义好之后是不可修改的,但集合本身是可以增加三处元素,这意味着集合的元素只能是数字字符串及元组,并且每个元素只能出现一次.

集合使用花括号{}表示:

        集合名 = {元素1,元素2,...,元素n}

### 可变集合的添加
 add(): 一次添加单个元素.\
 updata():一次添加多个元素.
```py
set1 = {1,2,3,4,5}
set2 = {4,5,6,7}
set1.add(7)
print(set1)
set2.update('hello','world')
print(set2)
```

remove():删除指定的元素,如果不存在,会报错\
discard():删除指定的元素,如果不存在,不会报错\
pop():删除第一个元素,如果集合为空,会报错
```py
set1 = {1,2,3,4,5}
set1.remove(2)
set1.remove(9)
print(set1)

set2 = {4,5,8,9}
ret = set2.pop()
print(ret)
```

可变集合元素的查找:\
in:使用关键字查找某元素是否存在于集合中.

部分其他操作:\
len():计算集合里元素个数\
set():生成一个集合\
copy():浅拷贝\
clear():清空集合\
intersection():求两个集合的交集\
union():求两个集合的并集\
issubset():求两个集合是不是子集关系\
issuperset():求两个集合是不是父集关系

```py
set1 = set('abc')
print(set1)
set2 = set1.copy()
print(set2)
#求交集
set3 = {4,5,6}
set4 = {1,2,3,4}
set5 ={1}
print(set3.intersection(set4))
#求并集
print(set3.union(set4))
#求关系
print(set5.issubset(set4))
print(set4.issuperset(set5))
```

## 每日一曲
<iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width=330px height=86px src="
https://i.y.qq.com/n2/m/outchain/player/index.html?songid=102204539&songtype=0"></iframe>



