# Python学习

**Writer:John Zheng**\
**Beginning Date:2024.2.27**

## 变量与简单的数据类型

### 变量名的使用

>1.组成：字母、数字、下划线\
2.开头可以是字母或下划线，但不可以是数字\
3.变量名中不可以含有空格，可以用下划线来分隔单词\
4.注意不可以将python关键字和函数名用作变量名\
5.变量名应当具有一定的描述性\
6.慎用含有小写字母l和大写字母O，因为可能会造成错看，以为是1和0\
7.使用变量时避免命名错误\
例 :`message="hello python crash course reader"`\
    `print(message)`\
效果：``hello python crash course reader``

## 字符串

**python中，字符串就是一系列字符，用引号扩起的都是字符串，其中单引号和双引号都就可以**\
例：``'this is a string'``\
或``"this is also a string"``

### 修改字符串的大小写

1.title()——以首字母大写的方式显示每个单词\
例：`name='zheng yuhang'`\
`print(name.title())`\
输出：``Zheng Yuhang``\
同理——\
2.upper()——全部大写\
3.lower()——全部小写

### 合并字符串

python使用+来合并字符串\
input:`first_name=yuhang`\
      `last_name=zheng`\
      `print(first_name+" "+last_name)`\
output:``yuhang zheng``\

### 使用制表符或换行符来添加空白

**\n,\t**\

### 删除空白

删除多余的空白\

```python
l1=' python '
print(l1.rstrip())
#rstrip()可以删除字符串末端多余的空格，但是这种删除只是暂时的，再次输出时依然有多余的空白
print(l1.lstrip())
#lstrip()删除字符串开头的空格
print(l1.strip())
#删除字符串两端的空格
```

### 使用字符串时应避免语法错误

* 当字符串中含由单引号时，应避免使用单引号来括起该字符串，而是使用双引号。
* 还有别的一些语法错误要注意

### 整数、浮点数

* 大致与c、c++相同\
* **表示乘方（即立方）运算\
* 浮点型运算结果包含的小数位数可能是不确定的，需要在学会处理多余小数的处理\

### 使用函数str（）可以避免类型错误

```python
age=12
print("happy "+age+"rd birthday")
#python将无法判断到底是12还是1还是2，会报错，正确的格式应该如下：
print("happy "+str(age)+"rd birthday")
```

### 注释！注释

略

## 列表

**列表的示例：**

```python
last_name_letter=['z','h','e','n','g']
print(last_name_letter)
print(last_name_letter[0])
```

output：``zheng z``\
注意：索引是从0开始而不是1，这一点等同于c或c++的数组

### **how to modify or add or delete**

```python
motorcycles=['honda','yamaha','suzuki']
print(motorcycles)

#modify
motorcycles[0]='ducati'
print(motorcycles)

#add——.append(字符串)
motorcycles.append('bba')
print(motorcycles)

#insert——使用函数.insert(位置，字符串)
motorcycles.insert(0,'ducati')
print(motorcycles)
```

```python
#delete——by using "del"
del motorcycles[0]
print(motorcycles)
```

```python
#delete——by using "pop()"
##什么时候用pop():将元素从列表里删除并接着用它的值。方法pop()可以删除列表末尾的元素，并可以接着使用该元素##
name=['zheng','john','yuhang']
print(name)
poped_name=name.pop()
print(name)
print(poped_name)
#output:['zheng','john','yuhang']
#zheng john
#yuahng
```

```python
#弹出列表任何位置的元素
#同样使用pop()
name1=name.pop(1)
print(name1)
print(name)
#john      zheng yuhang#
```

怎样判断时用del还是pop，根据你是否需要使用要删除的元素。

```python
#根据值删除元素
name=['zheng','john','yuhang']
print(name)
name.remove(yuhang)
print(name)
#output:zheng john yuhang
#       zheng john
english_name='john'
name.remove(english_name)
print(name)
#output:zheng
```

remove()只能删除第一个指定的值，如果存在多个相同的值，需要使用循环。

### 组织列表

#### 使用sort()对列表实现永久性排序

将列表按字母顺序排列：

```python
name=['zheng','yu','hang','john']
name.sort()
print(name)
```

output:``hang john yu zheng``

按字母顺序反序排列：\
使用reverse=Ture

```python
name.sort(reverse=Ture)
print(name)
```

output:``zheng yu john hang``

#### 使用函数sorted()对列表进行临时排序

使用情况：要保留原列表元素的顺序，又要以特定的顺序呈现它们。

```python
name=['zheng','yu','hang','john']
print(name)
print(sorted(name))
print(name)
```

output:zheng yu hang john*\
    hang john yu hang\
    zheng yu hang john\
同样也可以用reverse=Ture传递参数，实现反序列表\

#### 使用函数reverse()来倒着打印列表

```python
name=['zheng','yu','hang','john']
name.reverse()
print(name)
#output:john hang yu zheng
```

方法reverse()对列表的修改是永久性的。

#### 确定列表的长度

使用len()函数

```python
name=['zheng','yuhang']
print(len(name)+"个元素")
#output:2个元素
```

### 使用列表时避免索引错误

name[-1]指的是最后一个元素\
别的没什么好讲的，自己多注意。

## 操作列表

### 遍历整个列表

```python
names=['Yuhang','john']
for name in names:
    print(name)
#output:Yuhang john
```

name用于临时储存names的变量。\
选取有意义的名称更方便。

### for循环

for循环后面没有缩进的代码都执行一边，缩进的代码会多次打印至循环结束。

``for循环处理数据是一种对数据集执行整体操作的不错的方式。如可以用for循环来初始化游戏，遍历游戏列表，将每个角色都显示到屏幕上；再在循环后面添加一个不缩进的代码块，在屏幕上绘制所有角色后显示一个play now按钮。``

#### 避免错误的缩进

可能会出现的错误（千万要注意）：

* 忘记缩进
* 忘记缩进二外的代码行
* 不必要的缩进
* 循环后不必要的缩进
* for语句句末遗漏了冒号

### 创建数值列表

#### 使用函数range()

```python
#range()可以生成一系列数字
for value in range(1,5):
    print(value)
#上述代码好像会打印1~5，实际不会打印数字5
# output：1 2 3 4
#编程语言中常存在差一行为结果

#使用list()函数可以将range()的结果直接转换成列表
number=list(range(1,5))
print number
#output:[1,2,3,4]

#使用range()时还可以指定步长
#例如要打印1~10之间的偶数
even_numbers=list(range(2,11,2))
print(even_numbers)
#output:[2,4,6,8,10]

#函数range()几乎可以创建任何需要的数字集
```

#### 数字列表的简单统计计算

```python
digits=[1,2,3,4,5,6,7,8]
max(digits)
min(digits)
sum(digits)
```

#### 列表解析

简约的代码：**将for循环和创建新元素的代码合为一行，并自动附加新元素**

```python
squares=[value**2 for value in range(1,11)]
print(squares)
```

**步骤：**

* 首先指定一个描述性的列表名
* 指定一个左方括号，并定义一个表达式，用于生成你要储存到列表的值。
* 编写一个for循环，用于给表达式提供值，再加上右方括号

```python
#测试一：数到20
numbers=[number for number in range(1,21)]
print(numbers)

#测试二：创建一个列表包含1到1000000，使用min() and max()来核实确实是1到一百万，并调用sun()将它们相加
numbers=[number for number in range(1,1000001)]
print(min(numbers))
print(max(numbers))
print(sum(numbers))

#测试三：奇数
numbers=[number for number in range(1,21,2)]
print(numbers)

#测试四：三的倍数
threes=[number for number in range(3,31,3)]
print(threes)

#测试五：立方
lifang=[number**3 for number in range(1,11)]
for value in lifang:
    print(value)
#测试六：立方解析
print(lifang)
```

### 使用列表的一部分

#### 切片

>要创建切片，可指定要使用的第一个元素和最后一个元素的索引。同range(a,b)一样，在到达索引b前面的那一个元素后停止。要输出前三个元素，就要索引到第四个元素。

```python
players=['a','b','c','d','e','f']
print(players[0:3])
#output=['a','b','c']
```

>当无初始索引时(players[:3])，自动从列表开头开始。

```python
#需要输出后三个元素时：
players=['a','b','c','d','e','f']
print(players[-3:])
#output:['d','e','f']
```

```python
#遍历切片时
players=['a','b','c','d','e','f']
for player in players[:3]:
    print(player.title())
#output:A B C
```

#### 复制列表

怎样复制列表：**创建一个储存复制内容的列表，使其等于原列表的整个切片，即省略起始索引和终止索引**

```python
players=['a','b','c','d','e','f']
my_friend=players[:]
print(players)
print(my_friend)
#output:['a','b','c','d','e','f']
#       ['a','b','c','d','e','f']
```

>切记，不可以直接赋值令一方等于另一方，这样只是使两者相关联，使两个变量都指向同一个列表，改动其中一个，另一个也会随之改动。而复制列表的本质更接近于创建副本。

### 元组

>列表非常适合用于储存在程序运行期间可能变化的数据集，列表是可修改的。
>有时候需要创建一系列不可以修改的元素，python中将不能修改的值称为*不可变的*，而不可变的列表叫做**元组**。

定义元组：**元组形似列表，但是使用圆括号而非方括号来标识。**

```python
players=(1,2,3,4,5)
print(players[1])
for player in players:
    print(player)
#使用语法与访问列表元素时相同
#当试图令players[1]=3时，python会报错，提示无法修改
```

#### 修改元组变量

>元组中的元素不可修改，但可以给储存元组的变量赋值。因此，如果要修改元组中的元素，可以重新定义震哥哥元组。

```python
players=(1,2,3,4,5)
print(players[1])
for player in players:
    print(player)

players=(6,7,8,9,10)
print(players[1])
for player in players:
    print(player)
#output:2 1 2 3 4 5
#       7 6 7 8 9 10
```

### 设置代码格式

>代码被阅读的次数要比编写的次数要多。
>>无论是调试、添加新功能还是分享给别人时，都会阅读代码。

**注意事项：**

* 缩进普遍使用四个空格，在编辑器里可以自行设置不同的空格数。
* 每行建议最多不超过80字符。
* 使用空行将程序的不同部分分开，增加可读性。
* 推荐阅读PEP8指南，了解更多格式。

## if语句

>**简单的示例：**

```python
names=['zheng','john','yuhang']
for name in names:
    if name=='zheng':
        print(name +'is my last name.')
    else:
        print(name+' is my first name.')
```

```python
#检查变量的值是否相等
>>>car='toyota'
>>>car=='toyota'
output: True
>>>car=='bmw'
output:False
```

>检查是否相等时，区分大小写。但如果大小写无关紧要，只想检查变量的值，可以将变量的值利用函数lower()转化为小写，不考虑大小写。\
应用实例：在网站采用类似的手法，可以测试用户名是否独一无二，而非与另一用户名仅为大小写差异。

**如何检查是否不相等**可以用!=来运算。

**比较数字**可以直接使用各种数学比较。

## 字典

键—值对是两个相关联的值。指定键时，Python将返回与之相关联的值。键和值之间用冒号分隔，而键—值对之间用逗号分隔。在字典中，你想存储多少个键—值对都可以。\
最简单的字典只有一个键—值对，如下述修改后的字典alien_0所示：

```python
alien_0 = {'color': 'green'}
```

这个字典只存储了一项有关alien_0的信息，具体地说是这个外星人的颜色。在这个字典中，字符串'color'是一个键，与之相关联的值为'green'。\

含多个键的字典示例：

```python
alien_0 = {'color': 'green', 'points': 5} 
print(alien_0['color']) 
print(alien_0['points'])
```
---
```python
#访问字典中的值
print(alien_0['color'])

#添加键值对
alien_0 = {'color': 'green', 'points': 5} 
print(alien_0) 
alien_0['x_position'] = 0 
alien_0['y_position'] = 25 
print(alien_0)

#修改键值对
alien_0['x_position']=10

#删除键值对
del alien_0['points']
```
---

### 遍历字典

#### 遍历键与值

```python
user_0 = {
 'username': 'efermi', 
 'first': 'enrico', 
 'last': 'fermi', 
 }
for key, value in user_0.items(): 
    print("\nKey: " + key) 
    print("Value: " + value)
```
遍历字典时可声明两个变量。

#### 遍历所有键

在不需要使用字典中的值时，方法keys()很有用。下面来遍历字典favorite_languages，并将每个被调查者的名字都打印出来：

```python
favorite_languages = { 
 'jen': 'python', 
 'sarah': 'c', 
 'edward': 'ruby', 
 'phil': 'python', 
 }
for name in favorite_languages.keys(): 
    print(name.title())
```
#### 按顺序遍历字典中的所有键

要以特定的顺序返回元素，一种办法是在for循环中对返回的键进行排序。为此，可使用函数sorted()来获得按特定顺序排列的键列表的副本：

```python
favorite_languages = { 
 'jen': 'python', 
 'sarah': 'c', 
 'edward': 'ruby', 
 'phil': 'python', 
 } 
for name in sorted(favorite_languages.keys()): 
 print(name.title() + ", thank you for taking the poll.")
```

#### 遍历所有的值

如果你感兴趣的主要是字典包含的值，可使用方法values()，它返回一个值列表，而不包含任何键。例如，如果我们想获得一个这样的列表，即其中只包含被调查者选择的各种语言，而不包含被调查者的名字，可以这样做：

```python
favorite_languages = { 
 'jen': 'python', 
 'sarah': 'c', 
 'edward': 'ruby', 
 'phil': 'python', 
 } 
print("The following languages have been mentioned:") 
for language in favorite_languages.values(): 
 print(language.title())
```

通过对包含重复元素的列表调用set()，可让Python找出列表中独一无二的元素，并使用这些元素来创建一个集合。

```python
 for language in set(favorite_languages.values()):
```

#### 遍历字典列表

```python
alien_0 = {'color': 'green', 'points': 5} 
alien_1 = {'color': 'yellow', 'points': 10} 
alien_2 = {'color': 'red', 'points': 15} 
aliens = [alien_0, alien_1, alien_2] 
for alien in aliens: 
     print(alien)
```

### 嵌套

#### 在字典中储存列表

```python
 favorite_languages = { 
 'jen': ['python', 'ruby'], 
 'sarah': ['c'], 
 'edward': ['ruby', 'go'], 
 'phil': ['python', 'haskell'], 
 } 

 for name, languages in favorite_languages.items(): 
    print("\n" + name.title() + "'s favorite languages are:") 
    for language in languages: 
        print("\t" + language.title())
```

*注意：列表和字典的嵌套层级不应太多。如果嵌套层级比前面的示例多得多，很可能有更简单的解决问题的方案。*

#### 在字典中储存字典

```python
users = { 
 'aeinstein': { 
 'first': 'albert', 
 'last': 'einstein', 
 'location': 'princeton', 
 }, 
 'mcurie': { 
 'first': 'marie', 
 'last': 'curie', 
 'location': 'paris', 
 }, 
 } 
 for username, user_info in users.items(): 
    print("\nUsername: " + username) 
    full_name = user_info['first'] + " " +user_info['last'] 
    location = user_info['location'] 
    print("\tFull name: " + full_name.title()) 
    print("\tLocation: " + location.title())
 ```

## while语句

示例：

```python
 while True: 
 city = input(prompt) 
 if city == 'quit': 
 break 
 else: 
 print("I'd love to go to " + city.title() + "!")

 current_number = 0 
while current_number < 10:  
      current_number += 1 
    if current_number % 2 == 0: 
    continue 
    print(current_number)
```

