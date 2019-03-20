Python解释性

Python不需要编译为二进制码，而是转换为中间码，不用考量库的链接和编译，更加适合迁移

# Hello World

~~~python
print ("Hello World")
~~~

~~~python
Python 3.7.2 (tags/v3.7.2:9a3ffc0492, Dec 23 2018, 23:09:28) [MSC v.1916 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>> print ("Hello World")
Hello World
~~~

# 注释

~~~python
print('hello world') #注意到print是一个函数
~~~

- 解释假设
- 说明重要的决定
- 解释重要的细节
- 说明你想要解决的问题
- 说明你想要在程序中克服的问题，等等。

# 字面常量

数字：123

字符串：“This is a string”

# 数字

int: 2  没有long int 可以表示任意大小

float 2.2

# 字符串

## 单引号

’Quote me on this ‘

引号内空间 如：空格，制表符 原样保留

## 双引号

与单引号相同

## 三引号

’‘’

三引号内指定多行字符串，三引号之间自由使用单双引号

‘’‘

## 字符串是不可变的

## 格式化方法

~~~python
age = 20
name = 'Swaroop'
print('{0} was {1} years old when he wrote this book'.format(name, age))
print('Why is {0} playing with that python?'.format(name))
~~~

~~~
$ python str_format.py
Swaroop was 20 years old when he wrote this book
Why is Swaroop playing with that python?
~~~

一个字符串可以使用某些特定的格式（Specification），随后， format 方法将被调用，使用这一方法中与之相应的参数替换这些格式。在这里要注意我们第一次应用这一方法的地方，此处 {0} 对应的是变量 name ，它是该格式化方法中的第一个参数。与之类似，第二个格式 {1} 对应的是变量 age ，它是格式化方法
中的第二个参数。请注意，Python 从 0 开始计数，这意味着索引中的第一位是 0，第二位是1，以此类推。

```python
# 对于浮点数 '0.333' 保留小数点(.)后三位
print('{0:.3f}'.format(1.0/3))
# 使用下划线填充文本，并保持文字处于中间位置
# 使用 (^) 定义 '___hello___'字符串长度为 11
print('{0:_^11}'.format('hello'))
# 基于关键词输出 'Swaroop wrote A Byte of Python'
print('{name} wrote {book}'.format(name='Swaroop', book='A Byte of Python'))
```

print 总是会以一个不可见的“新一行”字符（ \n ）结尾，因此重复调用 print 将会在相互独立的一行中分别打印。为防止打印过程中出现这一换行符，你可以通过 end 指定其应以空白结尾：

```python
print('a', end='')
print('b', end='')
```

## 转义序列

"What's your name?"

- 使 Python 对于何处是字符串的开始、何处又是结束而感到困惑

转义序列（Escape Sequence） 来实现

'What\'s your name?'

在一个字符串中，一个放置在末尾的反斜杠表示字符串将在下一行继续，但不会添加新的一行

```python
"This is the first sentence. \
This is the second sentence."
```

```
"This is the first sentence. This is the second sentence."
```

## 原始字符串

如果你需要指定一些未经过特殊处理的字符串，比如转义序列，那么你需要在字符串前增加r 或 R 来指定一个 原始（Raw） 字符串

~~~python
r"Newlines are indicated by \n"
~~~

# 变量

### 标识符命名

开头字母下划线

其余数字字母下划线

大小写区分

```python
# 文件名：var.py
i = 5
print(i)
i = i + 1
print(i)
s = '''This is a multi-line string.
This is the second line.'''
print(s)
```

```
5
6
This is a multi-line string.
This is the second line.
```

如果你有一行非常长的代码，你可以通过使用反斜杠将其拆分成多个物理行。这被称作显式行连接（Explicit Line Joining）

```python
i = \
5
```

在某些情况下，会存在一个隐含的假设，允许你不使用反斜杠。这一情况即逻辑行以括号开始，它可以是方括号或花括号，但不能是右括号。这被称作 隐式行连接（Implicit Line Joining）

### 缩进

在逻辑行的开头留下空白区（使用空格或制表符）用以确定各逻辑行的缩进级别，而后者又可用于确定语句的分组。

有一件事你需要记住：错误的缩进可能会导致错误

```python
i = 5
# 下面将发生错误，注意行首有一个空格
print('Value is', i)
print('I repeat, the value is', i)
```

```
File "whitespace.py", line 3
print('Value is', i)
^
IndentationError: unexpected indent
# 缩进错误：意外缩进
```

## 运算符

+ +（加）
  两个对象相加。
  3+5 则输出 8 。 'a' + 'b' 则输出 'ab' 。
- -（减）
  从一个数中减去另一个数，如果第一个操作数不存在，则假定为零。
  -5.2 将输出一个负数， 50 - 24 输出 26 。
* *（乘）
  给出两个数的乘积，或返回字符串重复指定次数后的结果。
  2 * 3 输出 6 。 'la' * 3 输出 'lalala' 。

* ** （乘方）

  返回 x 的 y 次方。
  3 ** 4 输出 81 （即 3 * 3 * 3 * 3 ）。

* / 除

  浮点除

* // 整除

* % （取模）

* << （左移）

* '>>'（右移）

* | （按位或）

* ^ （按位异或）

* ~ （按位取反）

* < （小于）

* '>'（大于）

* = （大于等于）

* == （等于）

* != （不等于）

* not （布尔“非”）

* and （布尔“与”）

* or （布尔“或”)

一种比较常见的操作是对一个变量进行一项数学运算并将运算得出的结果返回给这个变量，因此对于这类运算通常有如下的快捷表达方式：

```python
a = 2
a = a * 2
```

```python
a= 2
a*=2
```

### 求值顺序

- lambda ：Lambda 表达式
- if - else ：条件表达式
- or ：布尔“或”

- and ：布尔“与”
- not  ：布尔“非”
- in, not in, is, is not, <, <=, >, >=, !=, == ：
- |
- ^
- &
- <<>>
- +=
- */

# 控制流

~~~python
guess = int(input('Enter an integer : '))
if guess == number:
    # 新块从这里开始
    print('Congratulations, you guessed it.')
    print('(but you do not win any prizes!)')
# 新块在这里结束
elif guess < number:
    # 另一代码块
    print('No, it is a little higher than that')
    # 你可以在此做任何你希望在该代码块内进行的事情
else:
    print('No, it is a little lower than that')
    # 你必须通过猜测一个大于（>）设置数的数字来到达这里。
print('Done')
# 这最后一句语句将在
# if 语句执行完毕后执行。
~~~

我们为内置的 input 函数提供一串打印到屏幕上的字符串并等待用户的输入。一旦我们输入了某些内容并按下键盘上的 enter 键， input() 函数将以字符串的形式返回我们所输入的内容。然后我们通过 int 将这个字符串转换成一个整数并将其储存在变量 guess 中。实际上， int 是一个类（Class），但你现在你所需要知道的就是你可以使用它将一串字符串转换成一个整数（假设这个字符串的文本中含有一个有效的整数）。

**if 语句在结尾处包含一个冒号**

**elif 和 else 同样都必须有一个冒号在其逻辑行的末尾，后面跟着与它们相应的语句块**

### while 语句

while 语句能够让你在条件为真的前提下重复执行某块语句。 while 语句是 循环（Looping） 语句的一种。 while 语句同样可以拥有 else 子句作为可选选项。

~~~python
number = 23
running = True
while running:
    guess = int(input('Enter an integer : '))
    if guess == number:
        print('Congratulations, you guessed it.')
        # 这将导致 while 循环中止
        running = False
    elif guess < number:
    	print('No, it is a little higher than that.')
	else:
    	print('No, it is a little lower than that.')
else:
    print('The while loop is over.')
    # 在这里你可以做你想做的任何事
print('Done')
~~~

你可以在 while 循环中使用 else 从句。

```python
for i in range(1, 5):
	print(i)
else:
	print('The for loop is over')
```

range() 每次只会生成一个数字，如果你希望获得完整的数字列表，要在使用 range() 时调用 list() 。例如下面这样： list(range(5)) ，它将会返回 [0, 1, 2,3, 4]

~~~python
while True:
    s = input('Enter something : ')
    if s == 'quit':
   		break
    print('Length of the string is', len(s))
print('Done')
~~~

输入字符串的长度可以通过内置的 len 函数来找到。

```python
while True:
    s = input('Enter something : ')
    if s == 'quit':
    	break
    if len(s) < 3:
        print('Too small')
        continue
    print('Input is of sufficient length')
    # 自此处起继续进行其它任何处理
```

## 函数

```python
def say_hello():
    # 该块属于这一函数
    print('hello world')
    # 函数结束
say_hello() # 调用函数
say_hello() # 再次调用函数
```

```python
def print_max(a, b):
    if a > b:
    print(a, 'is maximum')
    elif a == b:
    print(a, 'is equal to', b)
    else:
    print(b, 'is maximum')
# 直接传递字面值
print_max(3, 4)
x = 5
y = 7
# 以参数的形式传递变量
print_max(x, y)
```

### 局部变量

当你在一个函数的定义中声明变量时，它们不会以任何方式与身处函数之外但具有相同名称的变量产生关系，也就是说，这些变量名只存在于函数这一局部（Local）。这被称为变量的作用域（Scope）。所有变量的作用域是它们被定义的块，从定义它们的名字的定义点开始



```python
x = 50
def func(x):
print('x is', x)
x = 2
print('Changed local x to', x)
func(x)
print('x is still', x)
```

### global 语句

如果你想给一个在程序顶层的变量赋值（也就是说它不存在于任何作用域中，无论是函数还是类），那么你必须告诉 Python 这一变量并非局部的，而是全局（Global）的。我们需要通过 global 语句来完成这件事。因为在不使用 global 语句的情况下，不可能为一个定义于函数之外的变量赋值。

```python
x = 50
def func():
global x
print('x is', x)
x = 2
print('Changed global x to', x)
func()
print('Value of x is', x)
```

### 默认参数值

对于一些函数来说，你可能为希望使一些参数可选并使用默认的值，以避免用户不想为他们提供值的情况。默认参数值可以有效帮助解决这一情况。你可以通过在函数定义时附加一个赋值运算符（ = ）来为参数指定默认参数值。

```python
def say(message, times=1):
print(message * times)
say('Hello')
say('World', 5)
```

### 关键字参数

**如果你有一些具有许多参数的函数，而你又希望只对其中的一些进行指定，那么你可以通过
命名它们来给这些参数赋值——这就是关键字参数（Keyword Arguments）——我们使用命
名（关键字）而非位置（一直以来我们所使用的方式）来指定函数中的参数。**

```
def func(a, b=5, c=10):
print('a is', a, 'and b is', b, 'and c is', c)
func(3, 7)
func(25, c=24)
func(c=50, a=100)
```

### 可变参数

有时你可能想定义的函数里面能够有任意数量的变量，也就是参数数量是可变的，这可以通过使用星号来实现

```python
def total(a=5, *numbers, **phonebook):
print('a', a)
#遍历元组中的所有项目
for single_item in numbers:
print('single_item', single_item)
#遍历字典中的所有项目
for first_part, second_part in phonebook.items():
print(first_part,second_part)
print(total(10,1,2,3,Jack=1123,John=2231,Inge=1560))
```

当我们声明一个诸如 *param 的星号参数时，从此处开始直到结束的所有位置参数
（Positional Arguments）都将被收集并汇集成一个称为“param”的元组（Tuple）。
类似地，当我们声明一个诸如 **param 的双星号参数时，从此处开始直至结束的所有关键字
参数都将被收集并汇集成一个名为 param 的字典（Dictionary）。

### return 语句

```python
def maximum(x, y):
if x > y:
return x
elif x == y:
return 'The numbers are equal'
else:
return y
print(maximum(2, 3))
```

要注意到如果 return 语句没有搭配任何一个值则代表着 返回 None 。 None 在 Python 中一
个特殊的类型，代表着虚无。举个例子， 它用于指示一个变量没有值，如果有值则它的值便
是 None（虚无） 。
每一个函数都在其末尾隐含了一句 return None ，除非你写了你自己的 return 语句。你可
以运行 print(some_function()) ，其中 some_function 函数不使用 return 语句，就像这
样：

```python
def some_function():
pass
#Python 中的 pass 语句用于指示一个没有内容的语句块。
```

### DocStrings

```python
def print_max(x, y):
'''打印两个数值中的最大数。
这两个数都应该是整数'''
# 如果可能，将其转换至整数类型
x = int(x)
y = int(y)
if x > y:
print(x, 'is maximum')
else:
print(y, 'is maximum')
print_max(3, 5)
print(print_max.__doc__)
```

函数的第一行逻辑行中的字符串是该函数的 文档字符串（DocString）。这里要注意文档字符串也适用于后面相关章节将提到的模块（Modules）与类（Class）

我们可以通过使用函数的 __doc__ （注意其中的双下划綫）属性（属于函数的名称）来获取函数 print_max 的文档字符串属性。只消记住 Python 将所有东西都视为一个对象，这其中
自然包括函数。我

## 模块

那么如果你想在你所编写的别的程序中重用一些函数的话，应该怎么办？正如你可能想象到的那样，答案是模块（Modules）

```python
import sys
print('The command line arguments are:')
for i in sys.argv:
print(i)
print('\n\nThe PYTHONPATH is', sys.path, '\n')
```

```
$ python module_using_sys.py we are arguments
The command line arguments are:
module_using_sys.py
we
are
arguments
The PYTHONPATH is ['/tmp/py',
# many entries here, not shown here
'/Library/Python/2.7/site-packages',
'/usr/local/lib/python2.7/site-packages']
```

首先，我们通过 import 语句导入 sys 模块。基本上，这句代码将转化为我们告诉 Python我们希望使用这一模块。 sys 模块包含了与 Python 解释器及其环境相关的功能，也就是所谓的系统功能（system）。当 Python 运行 import sys 这一语句时，它会开始寻找 sys 模块。在这一案例中，由于其是一个内置模块，因此 Python 知道应该在哪里找到它。
如果它不是一个已编译好的模块，即用 Python 编写的模块，那么 Python 解释器将从它的sys.path 变量所提供的目录中进行搜索。如果找到了对应模块，则该模块中的语句将在开始运行，并能够为你所使用。在这里需要注意的是，初始化工作只需在我们第一次导入模块时完成。
sys 模块中的 argv 变量通过使用点号予以指明，也就是sys.argv 这样的形式。它清晰地表明了这一名称是 sys 模块的一部分。这一处理方式的另一个优点是这个名称不会与你程序中的其它任何一个 argv 变量冲突。
sys.argv 变量是一系列字符串的列表（List）（列表将在后面的章节予以详细解释）。具体而言， sys.argv 包含了命令行参数（Command Line Arguments）这一列表，也就是使用命令行传递给你的程序的参数。如果你正在使用一款 IDE 来编写并运行这些程序，请在程序菜单中寻找相关指定命令行参数的选项。
在这里，当我们运行 python module_using_sys.py we are arguments 时，我们通过 python 命令来运行 module_using_sys.py 模块，后面的内容则是传递给程序的参数。 Python 将命令行参数存储在 sys.argv 变量中供我们使用。
在这里要记住的是，运行的脚本名称在 sys.argv 的列表中总会位列第一。因此，在这一案例中我们将会有如下对应关系： 'module_using_sys.py' 对应sys.argv[0] ， 'we' 对应sys.argv[1] ， 'are' 对应 sys.argv[2] ， 'arguments' 对应 sys.argv[3] 。要注意到Python 从 0 开始计数，而不是 1。

### from..import 语句

如果你希望直接将 argv 变量导入你的程序（为了避免每次都要输入 sys. ），那么你可以通过使用 from sys import argv 语句来实现这一点。

> 警告：一般来说，你应该尽量避免使用 from...import 语句，而去使用 import 语句。这是为了避免在你的程序中出现名称冲突，同时也为了使程序更加易读。

```
if __name__ == '__main__':
print('This program is being run by itself')
else:
print('I am being imported from another module')
```

```
$ python module_using_name.py
This program is being run by itself
$ python
>>> import module_using_name
I am being
```

```
def say_hi():
print('Hi, this is mymodule speaking.')
__version__ = '0.1'
```

下面是一个使用 from...import 语法的范本（保存为 mymodule_demo2.py ）：

```
from mymodule import say_hi, version
say_hi()
print('Version', version)
```

from mymodule import say_hi, __version__say_hi()
print('Version', __version__)mymodule_demo2.py 所输出的内容与 mymodule_demo.py 所输出的内容是一样的。
在这里需要注意的是，如果导入到 mymodule 中的模块里已经存在了 __version__ 这一名称，那将产生冲突。这可能是因为每个模块通常都会使用这一名称来声明它们各自的版本号。因此，我们大都推荐最好去使用 import 语句，尽管这会使你的程序变得稍微长一些。你还可以使用：from mymodule import *

### dir 函数

内置的 dir() 函数能够返回由对象所定义的名称列表。 如果这一对象是一个模块，则该列表会包括函数内所定义的函数、类与变量。

```
$ python
>>> import sys
# 给出 sys 模块中的属性名称
>>> dir(sys)
['__displayhook__', '__doc__',
'argv', 'builtin_module_names',
'version', 'version_info']
# 此处只展示部分条目
# 给出当前模块的属性名称
>>> dir()
['__builtins__', '__doc__',
'__name__', '__package__','sys']
# 创建一个新的变量 'a'
>>> a = 5
>>> dir()
['__builtins__', '__doc__', '__name__', '__package__', 'a']
# 删除或移除一个名称
>>> del a
>>> dir()
['__builtins__', '__doc__', '__name__', '__package__']
```

### 包

包是指一个包含模块与一个特殊的 __init__.py 文件的文件夹，后者向 Python 表明这一文件夹是特别的，因为其包含了 Python 模块。

- <some folder present in the sys.path>/
- world/
- __init__.py
- asia/
- __init__.py
- india/
- __init__.py
- foo.py
- africa/
- __init__.py
- madagascar/
- __init__.py
- bar.py

### 数据结构

Python 中有四种内置的数据结构——列表（List）、元组（Tuple）、字典（Dictionary）和集合（Set）

#### 列表

[1,2,3,4]

一个类也可以带有方法（Method），也就是说对这个类定义仅对于它启用某个函数。只有当你拥有一个属于该类的对象时，你才能使用这些功能。举个例子，Python 为 list 类提供了一种 append 方法，能够允许你向列表末尾添加一个项目。例如 mylist.append('an item')将会向列表 mylist 添加一串字符串。在这里要注意到我们通过使用点号的方法来访问对象。

```python
# This is my shopping list
shoplist = ['apple', 'mango', 'carrot', 'banana']
print('I have', len(shoplist), 'items to purchase.')
print('These items are:', end=' ')
for item in shoplist:
print(item, end=' ')
print('\nI also have to buy rice.')
shoplist.append('rice')
print('My shopping list is now', shoplist)
print('I will sort my list now')
shoplist.sort()
print('Sorted shopping list is', shoplist)
print('The first item I will buy is', shoplist[0])
olditem = shoplist[0]
del shoplist[0]
print('I bought the', olditem)
print('My shopping list is now', shoplist)
```

#### 元组

元组（Tuple）用于将多个对象保存到一起。你可以将它们近似地看作列表，但是元组不能提供列表类能够提供给你的广泛的功能。元组的一大特征类似于字符串，它们是不可变的，也就是说，你不能编辑或更改元组。

```python
# 我会推荐你总是使用括号
# 来指明元组的开始与结束
# 尽管括号是一个可选选项。
# 明了胜过晦涩，显式优于隐式。
zoo = ('python', 'elephant', 'penguin')
print('Number of animals in the zoo is', len(zoo))
new_zoo = 'monkey', 'camel', zoo
print('Number of cages in the new zoo is', len(new_zoo))
print('All animals in new zoo are', new_zoo)
print('Animals brought from old zoo are', new_zoo[2])
print('Last animal brought from old zoo is', new_zoo[2][2])
print('Number of animals in the new zoo is',
len(new_zoo)-1+len(new_zoo[2]))
```

>
>
>包含 0 或 1 个项目的元组
>一个空的元组由一对圆括号构成，就像 myempty = () 这样。然而，一个只拥有一个项目的元组并不像这样简单。你必须在第一个（也是唯一一个）项目的后面加上一个逗号来指定它，如此一来 Python 才可以识别出在这个表达式想表达的究竟是一个元组还是只是一个被括号所环绕的对象，也就是说，如果你想指定一个包含项目 2 的元组，你必须指定 singleton = (2, ) 。

#### 字典

在字典中，你可以通过使用符号构成 d = {key : value1 , key2 : value2} 这样的形式，来成对地指定键值与值。在这里要注意到成对的键值与值之间使用冒号分隔，而每一对键值与值则使用逗号进行区分，它们全都由一对花括号括起。

```python
# “ab”是地址（Address）簿（Book）的缩写
ab = {
'Swaroop': 'swaroop@swaroopch.com',
'Larry': 'larry@wall.org',
'Matsumoto': 'matz@ruby-lang.org',
'Spammer': 'spammer@hotmail.com'
}
print("Swaroop's address is", ab['Swaroop'])
# 删除一对键值—值配对
del ab['Spammer']
print('\nThere are {} contacts in the address-book\n'.format(len(ab)))
for name, address in ab.items():
print('Contact {} at {}'.format(name, address))
# 添加一对键值—值配对
ab['Guido'] = 'guido@python.org'
if 'Guido' in ab:
print("\nGuido's address is", ab['Guido'])
```

#### 序列

```python
shoplist = ['apple', 'mango', 'carrot', 'banana']
name = 'swaroop'
# Indexing or 'Subscription' operation #
# 索引或“下标（Subscription）”操作符 #
print('Item 0 is', shoplist[0])
print('Item 1 is', shoplist[1])
print('Item 2 is', shoplist[2])
print('Item 3 is', shoplist[3])
print('Item -1 is', shoplist[-1])
print('Item -2 is', shoplist[-2])
print('Character 0 is', name[0])
# Slicing on a list #
print('Item 1 to 3 is', shoplist[1:3])
print('Item 2 to end is', shoplist[2:])
print('Item 1 to -1 is', shoplist[1:-1])
print('Item start to end is', shoplist[:])
# 从某一字符串中切片 #
print('characters 1 to 3 is', name[1:3])
print('characters 2 to end is', name[2:])
print('characters 1 to -1 is', name[1:-1])
print('characters start to end is', name[:])
```

```
$ python ds_seq.py
Item 0 is apple
Item 1 is mango
Item 2 is carrot
Item 3 is banana
Item -1 is banana
Item -2 is carrot
Character 0 is s
Item 1 to 3 is ['mango', 'carrot']
Item 2 to end is ['carrot', 'banana']
Item 1 to -1 is ['mango', 'carrot']
Item start to end is ['apple', 'mango', 'carrot', 'banana']
characters 1 to 3 is wa
characters 2 to end is aroop
characters 1 to -1 is waroo
characters start to end is swaroop
```

首先，我们已经了解了如何通过使用索引来获取序列中的各个项目。这也被称作下标操作（Subscription Operation）。如上所示，每当你在方括号中为序列指定一个数字，Python 将
获取序列中与该位置编号相对应的项目。要记得 Python 从 0 开始计数。因此 shoplist[0]将获得 shoplist 序列中的第一个项目，而 shoplist[3] 将获得第四个项目。

索引操作也可以使用负数，在这种情况下，位置计数将从队列的末尾开始。因此， shoplist[-1] 指的是序列的最后一个项目， shoplist[-2] 将获取序列中倒数第二个项目。

在切片操作中，第一个数字（冒号前面的那位）指的是切片开始的位置，第二个数字（冒号后面的那位）指的是切片结束的位置。如果第一位数字没有指定，Python 将会从序列的起始
处开始操作。如果第二个数字留空，Python 将会在序列的末尾结束操作。要注意的是切片操作会在开始处返回 start，并在 end 前面的位置结束工作。也就是说，序列切片将包括起始位
置，但不包括结束位置。

你同样可以在切片操作中提供第三个参数，这一参数将被视为切片的步长（Step）（在默认情况下，步长大小为1)

### 集合

>>> bri = set(['brazil', 'russia', 'india'])
>>> 'india' in bri
>>> True
>>> 'usa' in bri
>>> False
>>> bric = bri.copy()
>>> bric.add('china')
>>> bric.issuperset(bri)
>>> True
>>> bri.remove('russia')
>>> bri & bric # OR bri.intersection(bric)
>>> {'brazil', 'india'}

```python
print('Simple Assignment')
shoplist = ['apple', 'mango', 'carrot', 'banana']
# mylist 只是指向同一对象的另一种名称
mylist = shoplist
# 我购买了第一项项目，所以我将其从列表中删除
del shoplist[0]
print('shoplist is', shoplist)
print('mylist is', mylist)
# 注意到 shoplist 和 mylist 二者都
# 打印出了其中都没有 apple 的同样的列表，以此我们确认
# 它们指向的是同一个对象
print('Copy by making a full slice')
# 通过生成一份完整的切片制作一份列表的副本
mylist = shoplist[:]
# 删除第一个项目
del mylist[0]
print('shoplist is', shoplist)
print('mylist is', mylist)
# 注意到现在两份列表已出现不同
```

```
$ python ds_reference.py
Simple Assignment
shoplist is ['mango', 'carrot', 'banana']
mylist is ['mango', 'carrot', 'banana']
Copy by making a full slice
shoplist is ['mango', 'carrot', 'banana']
mylist is ['carrot', 'banana']
```

```python
# 这是一个字符串对象
name = 'Swaroop'
if name.startswith('Swa'):
print('Yes, the string starts with "Swa"')
if 'a' in name:
print('Yes, it contains the string "a"')
if name.find('war') != -1:
print('Yes, it contains the string "war"')
delimiter = '_*_'
mylist = ['Brazil', 'Russia', 'India', 'China']
print(delimiter.join(mylist))
```

### 面向对象编程

在至今我们编写的所有程序中，我们曾围绕函数设计我们的程序，也就是那些能够处理数据的代码块。这被称作面向过程（Procedure-oriented）的编程方式。还有另外一种组织起你的程序的方式，它将数据与功能进行组合，并将其包装在被称作“对象”的东西内。在大多数情况下，你可以使用过程式编程，但是当你需要编写一个大型程序或面对某一更适合此方法的问题时，你可以考虑使用面向对象式的编程技术。



类与对象是面向对象编程的两个主要方面。一个类（Class）能够创建一种新的类型（Type），其中对象（Object）就是类的实例（Instance）。可以这样来类比：你可以拥有类型 int 的变量，也就是说存储整数的变量是 int 类的实例（对象）。

对象可以使用属于它的普通变量来存储数据。这种从属于对象或类的变量叫作字段（Field）。对象还可以使用属于类的函数来实现某些功能，这种函数叫作类的方法（Method）

字段有两种类型——它们属于某一类的各个实例或对象，或是从属于某一类本身。它们被分别称作实例变量（Instance Variables）与类变量（Class Variables）

### self

类方法与普通函数只有一种特定的区别——前者必须多加一个参数在参数列表开头，这个名字必须添加到参数列表的开头，但是你不用在你调用这个功能时为这个参数赋值，Python 会为它提供。这种特定的变量引用的是对象本身，按照惯例，它被赋予 self 这一名称。

### 类

```
class Person:
pass # 一个空的代码块
p = Person()
print(p)
```

```
$ python oop_simplestclass.py
<__main__.Person instance at 0x10171f518>
```

### '_init_'___ 方法

```
class Person:
def __init__(self, name):
self.name = name
def say_hi(self):
print('Hello, my name is', self.name)
p = Person('Swaroop')
p.say_hi()
```

字段（Field）有两种类型——类变量与对象变量，它们根据究竟是类还是对象拥有这些变量来进行分类。
类变量（Class Variable）是共享的（Shared）——它们可以被属于该类的所有实例访问。
该类变量只拥有一个副本，当任何一个对象对类变量作出改变时，发生的变动将在其它所有
实例中都会得到体现。对象变量（Object variable）由类的每一个独立的对象或实例所拥有。在这种情况下，每个对象都拥有属于它自己的字段的副本，也就是说，它们不会被共享，也不会以任何方式与其它不同实例中的相同名称的字段产生关联。下面一个例子可以帮助你理解（保存为

```python
# 一个类变量，用来计数机器人的数量
population = 0
def __init__(self, name):
"""初始化数据"""
self.name = name
print("(Initializing {})".format(self.name))
# 当有人被创建时，机器人
# 将会增加人口数量
Robot.population += 1
def die(self):
"""我挂了。"""
print("{} is being destroyed!".format(self.name))
Robot.population -= 1
if Robot.population == 0:
print("{} was the last one.".format(self.name))
else:
print("There are still {:d} robots working.".format(
Robot.population))
def say_hi(self):
"""来自机器人的诚挚问候
没问题，你做得到。"""
print("Greetings, my masters call me {}.".format(self.name))
@classmethod
def how_many(cls):
"""打印出当前的人口数量"""
print("We have {:d} robots.".format(cls.population))
droid1 = Robot("R2-D2")
droid1.say_hi()
Robot.how_many()
droid2 = Robot("C-3PO")
droid2.say_hi()
Robot.how_many()
print("\nRobots can do some work here.\n")
print("Robots have finished their work. So let's destroy them.")
droid1.die()
droid2.die()
Robot.how_many()
```

这是一个比较长的案例，但是它有助于展现类与对象变量的本质。在本例中， population 属于 Robot 类，因此它是一个类变量。 name 变量属于一个对象（通过使用 self 分配），因此它是一个对象变量。

我们使用装饰器（Decorator）将 how_many 方法标记为类方法。你可以将装饰器想象为调用一个包装器（Wrapper）函数的快捷方式，因此启用@classmethod 装饰器等价于调用：

how_many = classmethod(how_many)

因此，你需要遵循这样的约定：任何在类或对象之中使用的变量其命名应以下划线开头，其它所有非此格式的名称都将是公开的，并可以为其它任何类或对象所使用。请记得这只是一个约定，Python 并不强制如此（除了双下划线前缀这点）。

### 继承

面向对象编程的一大优点是对代码的重用（Reuse），重用的一种实现方法就是通过继承
（Inheritance）机制。继承最好是想象成在类之间实现类型与子类型（Type and Subtype）
关系的工具。

# 输入与输出

有些时候你的程序会与用户产生交互。举个例子，你会希望获取用户的输入内容，并向用户打印出一些返回的结果。我们可以分别通过 input() 函数与 print 函数来实现这一需求。

```python
poem = '''\
Programming is fun
When the work is done
if you wanna make your work also fun:
use Python!
'''
# 打开文件以编辑（'w'riting）
f = open('poem.txt', 'w')
# 向文件中编写文本
f.write(poem)
# 关闭文件
f.close()
# 如果没有特别指定，
# 将假定启用默认的阅读（'r'ead）模式
f = open('poem.txt')
while True:
line = f.readline()
# 零长度指示 EOF
if len(line) == 0:
break
# 每行（`line`）的末尾
# 都已经有了换行符
#因为它是从一个文件中进行读取的
print(line, end='')
# 关闭文件
f.close()
```

首先，我们使用内置的 open 函数并指定文件名以及我们所希望使用的打开模式来打开一个文件。打开模式可以是阅读模式（ 'r' ），写入模式（ 'w' ）和追加模式（ 'a' ）。我们还可以选择是通过文本模式（ 't' ）还是二进制模式（ 'b' ）来读取、写入或追加文本。实际上还有其它更多的模式可用， help(open) 会给你有关它们的更多细节。在默认情况下， open() 会将文件视作文本（text）文件，并以阅读（read）模式打开它。在我们的案例中，我们首先采用写入模式打开文件并使用文件对象的 write 方法来写入文件，并在最后通过 close 关闭文件。输入与输出


# 异常

```python
>>> Print("Hello World")
Traceback (most recent call last):
File "<stdin>", line 1, in <module>
NameError: name 'Print' is not defined
>>> print("Hello World")
Hello World
```

我们将所有可能引发异常或错误的语句放在 try 代码块中，并将相应的错误或异常的处理器（Handler）放在 except 子句或代码块中。 except 子句可以处理某种特定的错误或异常，
或者是一个在括号中列出的错误或异常。如果没有提供错误或异常的名称，它将处理所有错误与异常。
要注意到必须至少有一句 except 字句与每一句 try 字句相关联。不然，有一个 try 代码块又有什么意义？
如果没有任何错误或异常被处理，那么将调用 Python 默认处理器，它只会终端程序执行并打印出错误信息。我们已经在前面的章节里见过了这种处理方式。
你还可以拥有一个 else 子句与 try..except 代码块相关联。 else 子句将在没有发生异常的时候执行。

## 抛出异常

你可以通过 raise 语句来引发一次异常，具体方法是提供错误名或异常名以及要抛出（Thrown）异常的对象。

```python
# encoding=UTF-8
class ShortInputException(Exception):
'''一个由用户定义的异常类'''
def __init__(self, length, atleast):
Exception.__init__(self)
self.length = length
self.atleast = atleast
try:
text = input('Enter something --> ')
if len(text) < 3:
raise ShortInputException(len(text), 3)
# 其他工作能在此处继续正常运行
except EOFError:
print('Why did you do an EOF on me?')
except ShortInputException as ex:
print(('ShortInputException: The input was ' +
'{0} long, expected at least {1}')
.format(ex.length, ex.atleast))
else:
print('No exception was raised.')
```

```
import sys
import time
f = None
try:
f = open("poem.txt")
# 我们常用的文件阅读风格
while True:
line = f.readline()
if len(line) == 0:
break
print(line, end='')
sys.stdout.flush()
print("Press ctrl+c now")
# 为了确保它能运行一段时间
time.sleep(2)
except IOError:
print("Could not find file poem.txt")
except KeyboardInterrupt:
print("!! You cancelled the reading from the file.")
finally:
if f:
f.close()
print("(Cleaning up: Closed the file)")
```

### with 语句

```
with open("poem.txt") as f:
for line in f:
print(line, end='')
```

程序输出的内容应与上一个案例所呈现的相同。本例的不同之处在于我们使用的是 open 函数与 with 语句——我们将关闭文件的操作交由 with open 来自动完成。在幕后发生的事情是有一项 with 语句所使用的协议（Protocol）。它会获取由 open 语句返回的对象，在本案例中就是“thefile”。
它总会在代码块开始之前调用 thefile.__enter__ 函数，并且总会在代码块执行完毕之后调用 thefile.__exit__ 。
因此，我们在 finally 代码块中编写的代码应该格外留心 __exit__ 方法的自动操作。这能够帮助我们避免重复显式使用 try..finally 语句。有关该话题的更多讨论已经超出了本书所能涉及的范围，因此请参考 PEP 343 来了解更加全面的解释。

### Lambda 表格

```
points = [{'x': 2, 'y': 3},
{'x': 4, 'y': 1}]
points.sort(key=lambda i: i['y'])
print(points)
```

### 列表推导

```
listone = [2, 3, 4]
listtwo = [2*i for i in listone if i > 2]
print(listtwo)
```

### 在函数中接收元组与字典

有一种特殊方法，即分别使用 * 或 ** 作为元组或字典的前缀，来使它们作为一个参数为函数所接收。当函数需要一个可变数量的实参时，这将颇为有用。

### assert 语句

你应该明智地选用 assert 语句。在大多数情况下，它好过捕获异常，也好过定位问题或向用户显示错误信息然后退出。

```
>>> mylist = ['item']
>>> assert len(mylist) >= 1
>>> mylist.pop()
'item'
>>> assert len(mylist) >= 1
Traceback (most recent call last):
File "<stdin>", line 1, in <module>
AssertionError
```

### 装饰器

装饰器（Decorators）是应用包装函数的快捷方式。这有助于将某一功能与一些代码一遍又一遍地“包装”。举个例子，我为自己创建了一个 retry 装饰器，这样我可以将其运用到任何函
数之中，如果在一次运行中抛出了任何错误，它就会尝试重新运行，直到最大次数 5 次，并且每次运行期间都会有一定的延迟。这对于你在对一台远程计算机进行网络调用的情况十分
有用：