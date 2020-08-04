# Python笔记

#号为注释

```python
# this is a comment text
```

多行注释`'''    '''`

```python
'''
这是一行注释
这也是一行注释
'''
```



IDLE为Python的交互式界面也叫做shell界面

交互式-- 一问一答的解释性语言（一行一行的执行）

print(你需要输出的语句)

```python
>>>print("This is my first experience to study python language")
This is my first experience to study python language
>>>print(1+2)
3

print("www","baidu","com",sep=".")  #以.作为连接符，输出：www.bai.com
print("hello",end="")      #end 以什么结束，若为空则不换行连接输出
print("world",end="\t")   #该语句输出：helloworld    python
print("python")
```

*用在字符串里表示重复操作符 

```python
>>>print("fuck"*3)
fuckfuckfuck
```

input()输入函数

```python
>>>t=input("test")
>>>print(t)
test
```

input输入的均为字符串，若想输入其他形式则先强制进行转换

```python
>>>x=int(input("123"))
>>>print(x)
123
```

```python
>>>a=1
>>>type(a)  #输出a的数据类型
>>><class 'int'>    #class为未定义数据
```

输出文字信息的同时需要引入数据，则使用格式化操作符%

```python
>>>name="Briz"
>>>print("my name is %s"%name)
>>>my name is Briz
```

if条件语句:两个数比大小

```python
num1=int(input("Input a digital:"))
num2=int(input("Input another digital:"))
if num1==num2:
    print("euqal!")
elif num1>num2:
    print(num1)
else:
    print(num2)
```

三个数比大小

```python
num1=int(input("Input a digital:"))
num2=int(input("Input another digital:"))
num3=int(input("Input last digital:"))
if num1==num2:
    print("euqal!")
elif (num1>num2) and (num1>num3):
    print(num1)
elif(num2>num1) and (num2>num3):
    print(num2)
else:
    print(num3)
```

if实例：石头剪刀布小游戏

```python
import random    #引入随机库
AI=random.randint(0,2)  #随机生成0-2之间的随机数
x=int(input("Please input:scissors is 0,stone is 1,cloth is 2: "))
if x>=0 and x<3:
    if (x==0 and AI==1)or(x==1 and AI==2)or(x==2 and AI==0):
        print("AI's input:%d,You are failed!"%AI)
    elif (x==AI):
        print("AI's input:%d,You are tied!"%AI)
    else:
        print("AI's input:%d,You are tied!"%AI)
else:
    print("You are out of range!")
```

for循环语句 for i in range(start,stop,step) 

> start--起始值  stop--终止值  step--增减值

```python
sum=0
for i in range(1,101,1):  #在1到101范围以1递增
    sum+=i
print(sum)   #此处应注意别将print语句写入循环
```

```python
>>>for i in range(5):
    print(i,end=" ")    #以空格分隔，不然默认会换行
0 1 2 3 4

name="Love U!"
for i in name:
    print(i,end="\t")
    
a=["aa","bb","cc","dd"]
for i in range(len(a)):  #len()得到元组长度的函数
    print(i,a[i])
```

break，continue和pass(占位语句无作用)

```python
word=LOVE
for i in word:
    	if i=="V":
            	break
            print(i)
L
O

for i in word:
    	if i=="V":
            	continue
            print(i)
L
O
E
```

while 条件循环

```python
>>>num=[1,2,3,4,4,4,4,4]
>>>while 4 in num
>>>num.remove(4)
>>>num
[1,2,3]
```

打印9*9乘法表

```python
for i in range(1,10,1):
    for j in range(1, i + 1, 1):
        print("%d*%d=%d" % (i, j, i*j),end=" ")
    print("")
```

字符串

```python
str="This is a text"
print(str[0:7])  #打印0-6个字符
This is
print(str[0:7:2])  #打印0-6个字符但每隔两个字符打印一次
Ti s
print("this\tis")
this	is
print(r"this\tis")
this\tis    #字符串前加r使里面的转义失效并直接显示
print("hello "+"world")
hello world    #字符连接使用+
```

列表 list[]

```python
>>>#创建一个普通的列表
>>>songs=["Green Light","Sober","Liability","Write in the dark"]
>>>print(songs)
["Green Light","Sober","Liability","Write in the dark"]
>>>songs[1]
"Sober"

>>>#创建一个混合的列表
>>>mix_lists=["1","2","test","4"]

>>>#默认函数list：把参数生成一个列表
>>>name="Briz"
>>>list(name)
>>>["B","r","i","z"]

#若已经使用list关键字定义了一个列表，则不能再次使用list函数
#因此不建议使用list创建列表，但可以用list1等

>>>songs=["Green Light","Sober","Liability","Write in the dark"]
>>>songs
["Green Light","Sober","Liability","Write in the dark"]
>>>songs.append("Perfect Place")
#无反馈但是append函数已经生效
>>>songs
["Green Light","Sober","Liability","Write in the dark","Perfect Place"]

a=[1,2]
b=[3,4]
a.append(b)
print(a)
[1, 2, [3, 4]]    #b列表被当成一个元素即a[2]加入a列表
#append()函数默认向列表最后添加一个元素--入栈

>>>songs.extend(["Royals","The Louvre"])
>>>songs
["Green Light","Sober","Liability","Write in the dark","Royals","The Louvre"]
#extend()默认用一个新的列表拓展原列表

>>>songs.insert(1,"Supercut")
>>>songs
["Green Light","Supercut","Sober","Liability","Write in the dark","Royals","The Louvre"]
#insert()在第几项元素插入新元素

>>>songs.remove("Sober")
>>>songs
["Green Light","Liability","Write in the dark","Royals","The Louvre"]
#remove() 删除列表的值

>>>songs.pop()
"The Louvre"
#pop() 默认删除末尾最后一个元素，并且有返还值
>>>songs.pop(5)
"Royals"
#指定删除某项元素
>>>del songs(0)
"Green Light"
#与上面同样效果
>>>del songs
>>>songs
#删除整个列表
```

拼接操作符+（两边的数据类型必须一致）

```python
>>>num1=[1,2]
>>>num2=[100,200]
>>>num1+num2
>>>[1,2,100,200]
```

列表的成员检查操作符 in

```python
>>>num=[1,2,True,[1,2,3,4]]   #列表1234在列表num的第四个元素
>>>1 in num
True
>>>3 in num
False     #3在num的第四号元素里
>>>3 in num[3]
True

songs=["Green Light","Sober","Liability","Write in the dark"]
findsong=input("Please input a song that you want to find:")
if findsong in songs:
   print("It is existed")
else:
   print("It is not existed")

songs=["Green Light","Sober","Liability","Write in the dark"]
print(songs.index("Sober",0,2))
1    #查找指定范围的元素并返回相应数据的下标，且左闭右开区间
```

拷贝

```python
#赋值拷贝 浅拷贝
>>>num=[4,3,2,1]
>>>num1=num
>>>num1
[4,3,2,1]
#切片拷贝 深拷贝
>>>num2=num[:]
>>>num2
>>>[4,3,2,1]
#升序排序
>>>num.sort()
>>>num
>>>[1,2,3,4]
>>>num1
>>>[1,2,3,4]
>>>num2
>>>[4,3,2,1]   
#通过赋值拷贝的列表会随着原列表的改变而改变
#而切片拷贝则是完整拷贝且值不会随着原列表的改变而改变
```

count() 计数函数

```python
>>>num=[1,1,1,2,3]
>>>num.count(1)
>>>3
```

reverse() 反转函数

```python
>>>num=[1,2,3,4]
>>>num.reserve()
>>>num
[4,3,2,1]
```

sort()排序函数

```python
a=[3,5,1,2]
a.sort()
print(a)
[1,2,3,5]
a.sort(reverse=True)
print(a)
[5,3,2,1]
```

list实例：

> ---- Product list ----
> 0  iPhone    6888 
> 1  MacPro   14800 
> 2  Mi6        2499 
> 3  NIKE       699 
> 4  Vans       499 
> 5  adidas     399  
>
> 打印上面的products列表并写一个循环，不断询问用户想买什么，用户选择一个商品编号，就把对应的商品添加到购物车里，最终用户输入q退出时，打印购买的商品列表并计算总价。

```python
products=[["iPhone",6888],["MacPro",14800],["Mi6",2499],["NIKE",699],["Vans",499],["adidas",399]]
print("---- Product list ----")
for i in range(0,6):
    print("%d  %-6s  %-6d"%(i,products[i][0],products[i][1]))
shop=[]
sum=0
i=1
while i!=0:
    p = input("Please input product's number to buy it:")
    if p=="q":
        x=input("Are you sure to settle the product? y/n:")
        if x=="y":
            print("---- Your shopping cart ----")
            for n in shop:
                print("%s  %s" % (products[n][0], products[n][1]))
            print("You need to pay:%d" % sum)
            break
        else:
            continue
    elif p>"0" and p<"6":
        p=int(p)
        shop.append(p)
        sum += products[p][1]
        print("Add to Cart successful!")
    else:
        print("Please input the currect product's number!")
```

元组 tuple()

```python
#元组也是一种列表但是为只读列表
>>>tuple1=(1,2,3,4)
>>>tuple1
(1,2,3,4)
>>>tuple2=(1)
>>>tuple2
1
>>>tuple3=1,
>>>tuple3
(1,)
#, 逗号是元组的标识符 创建只有一个元素的元组时末尾应加上,逗号
#创建一个空元组
>>>tuple4=()
>>>tuple4
()

tup1=(1,2,3)
tup2=("a","b")
tup=tup1+tup2
print(tup)
(1, 2, 3, 'a', 'b')
#虽不可修改但可以连接
```

字典 dict

````python
>>>dict1={1:11,ab:"test"}
>>>dict1
{1:11,ab:"text"}
>>># 访问字典元素的值与列表和元组相同，但列表和元组通过下标索引来取值
>>>#字典就是通过key键来取值
>>>dict1[ab]
"text"
>>>#快速定义字典
>>>name=["Briz","Jixy"]
>>>sign=["1","2"]
>>>dict2=dict(zip(name,sign))
>>>dict2
{"Briz":"1","Jixy":"2"}

info={"name":"Briz","age":20}
#print(info["gender"])    #直接访问不存在的键会报错
print(info.get("gender"))    #使用get方法若没有找到对应的键默认返回 None
print(info.get("gender","male"))    #若没找到可以设定默认值

None
male

info={"name":"Briz","age":20}
print(info.keys())    #打印全部键(列表形式)
print(info.values())    #打印全部的键对应的值(列表形式)
print(info.items())    #打印全部的键值(列表形式，且每个键值是一个元组)
info["id"]=12    #新增键值
info["age"]=18    #修改键值
del info["name"]    #删除键值
print(info)

dict_keys(['name', 'age'])
dict_values(['Briz', 20])
dict_items([('name', 'Briz'), ('age', 20)])
{'age': 18, 'id': 12}

info.clear()    #清空字典的值但保留空字典
del info    #删除info字典

#使用枚举函数
a=["a","b","c"]
for i,x in enumerate(a):
    print(i+1,x)
1 a
2 b
3 c
````

集合 set

```python
>>>set1={1,2,2,2,3,3,3,3,3}    #集合里的元素是不重复的
>>>set1
{1,2,3}    
```

lambda函数

```python
>>>lamdba a:a+8   ##定义一个函数
>>>d=lamdba a:a+8
>>>>d(1)   ##调用函数
9
```

类和对象

```python
class Turtle:   ##创建类Turtle
	def run(self):  ##用ABC替代self
		print("I run slowly")
        	print("my name is %s"%self.name)
	def sleep(self):
		print("I can sleep all day!")
        def __inti__(self):    ##__init__是一个专门给对象添加属性的方法，初始化属性
            self.name="托尼"
        def __del__(self):  ##当一个对象不再使用时进行销毁
            print("Had deleted!")
            
ABC=Turtle()         ##创建一个对象


>>> ABC.sleep()        ##调用Turtle类
I can sleep all day!
>>> ABC.run()
I run slowly
>>>ABC.name="Tony"
>>>ABC.run()
I run slowly
my name is Tony
```

`EG`:

```python
class Student:
    def __init__(self,name,age,grade):
        self.name=name
        self.age=age
        self.grade=grade
    def get_name(self):
        return self.name
    def get_age(self):
        return self.age
    def get_grade(self):
        return max(self.grade)

stu1=Student("Briz",20,[100,95,98])
print("Name:%s"%(stu1.get_name()))
print("Age:%d"%(stu1.get_age()))
print("Max grade:%s"%(stu1.get_grade()))

```

继承，重写与拓展

```python
class Animal:
    def eat(self):
        print("I can eat")
    def sleep(self):
        print("I can sleep")
class Dog(Animal):  ##子类后面跟父类则继承父类属性
    def bark(self):
        print("I can bark")

        
class Animal:
    def eat(self):
        print("I can eat")
    def sleep(self):
        print("I can sleep")
class Cat(Animal):  
    def eat(self):
        print("I only eat fish")     ##子类重写父类的eat属性其他属性不变
    def sleep(self):
        super().sleep()    ##对父类方法进行拓展，调用父类sleep属性的同时修改子类的特殊需求
        print("I sleep gently")
```

文件操作

```python
f=open("text.py","w")    #以只写的模式打开文件，若不存在则新建该文件
f.write("This is a text!")    #写入内容
f.close()    #关闭文件
#以上代码会生成一个text.txt的文本文件，并写入“This is a text!”

f=open("text.txt","r")
content=f.read(10)    #使用读模式读取10个字符
print(content)
f.close()
This is a 

f=open("text.txt","r")
content=f.readlines()    #一次读取全部文件为列表，f.readline()为一次打印一行
for t in content:
    print("%s"%t)
f.close()

This is a text!

This is a text!

This is a text!

This is a text!

This is a text!

import os    #引入os模块
os.rename("text.txt","1.txt")    #将text文本文件改名为1
os.remove("1.txt")    #删除1文本文件

```

> `访问模式说明` 
>
> r 以只读方式打开文件。文件的指针将会放在文件的开头。这是默认模式。 
>
> w 打开一个文件只用于写入。如果该文件已存在则将其覆盖。如果该文件不存在，创建新文 件。 
>
> a 打开一个文件用于追加。如果该文件已存在，文件指针将会放在文件的结尾。也就是说， 新的内容将会被写入到已有内容之后。如果该文件不存在，创建新文件进行写入。 
>
> rb 以二进制格式打开一个文件用于只读。文件指针将会放在文件的开头。这是默认模式。 
>
> wb 以二进制格式打开一个文件只用于写入。如果该文件已存在则将其覆盖。如果该文件不存 在，创建新文件。 
>
> ab 以二进制格式打开一个文件用于追加。如果该文件已存在，文件指针将会放在文件的结 尾。也就是说，新的内容将会被写入到已有内容之后。如果该文件不存在，创建新文件进 行写入。 
>
> r+ 打开一个文件用于读写。文件指针将会放在文件的开头。 
>
> w+ 打开一个文件用于读写。如果该文件已存在则将其覆盖。如果该文件不存在，创建新文 件。 
>
> a+ 打开一个文件用于读写。如果该文件已存在，文件指针将会放在文件的结尾。文件打开时 会是追加模式。如果该文件不存在，创建新文件用于读写。
>
>  rb+ 以二进制格式打开一个文件用于读写。文件指针将会放在文件的开头。
>
>  wb+ 以二进制格式打开一个文件用于读写。如果该文件已存在则将其覆盖。如果该文件不存 在，创建新文件。
>
>  ab+ 以二进制格式打开一个文件用于追加。如果该文件已存在，文件指针将会放在文件的结 尾。如果该文件不存在，创建新文件用于读写。

错误与异常

```python
try:
    print(name)
except Exception as result:    #异常类型捕获
    print("error!")
    print(result)
    
error!
name 'num' is not defined

try:
    try:
        print(num)
    finally:    #无论try内的语句有没有执行，finally内语句都会执行
        print("123")
except Exception as result:
    print(result)
    
123
name 'num' is not defined
```

实例：

> 1. 应用文件操作的相关知识，通过Python新建一个文件gushi.txt，选择一首古诗写入文件中
> 2. 另外写一个函数，读取指定文件gushi.txt，将内容复制到copy.txt中，并在控制台输出“复制完
>    毕”。
> 3. 提示：分别定义两个函数，完成读文件和写文件的操作，尽可能完善代码，添加异常处理。

```python
f=open("Liability.txt","w",encoding="utf-8")
f.write("春眠不觉晓\n处处闻啼鸟")
f.close()
def Read(file_name1):
    try:
        f=open(file_name1,"r",encoding="utf-8")
        try:
            while True:
                content=f.read()
                if content==0:
                    print("This document is not exisited!")
                    break
                print("Content has been copied!")
                return content
        finally:
            f.close()
    except Exception as result:
        print(result)
def Copy(content,file_name2):
    f = open(file_name2,"w",encoding="utf-8")
    f.write(content)
    print("Copy successully!")
    f.close()
file_name1 = input("Please input file's name:")
Content=Read(file_name1)
file_name2 = input("Please input file's name you want to copy:")
Copy(Content,file_name2)
```

计算出每行和，每列和，每行最大值，每行最小值和累计和

```python
import numpy

myarr=numpy.arange(12).reshape(3,4)
print(myarr)
print(myarr.sum(axis=0))  #每行和
print(myarr.sum(axis=1))  #每列和
print(myarr.max(axis=0))  #每行最大值
print(myarr.max(axis=1))  #每列最大值
print(myarr.cumsum(axis=0))  #每行累计和
```

降低数组的维度

```python
import numpy
arr=numpy.int32(100*numpy.random.rand(3,4))
arr1=arr.ravel()
print(arr)
print(arr1)

[[55 67 81 12]
 [80  2 84 72]
 [55 72 69 59]]
[55 67 81 12 80  2 84 72 55 72 69 59]
```

转置数组

```python
arr.shape=(6,2)
print(arr)
arr1=arr.transpose()
print(arr1)

[[51 42]
 [57 19]
 [66 26]
 [58 23]
 [39 95]
 [32  9]]
[[51 57 66 58 39 32]
 [42 19 26 23 95  9]]
```

