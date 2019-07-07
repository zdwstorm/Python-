# python笔记-进阶              <sub> —storm</sub>

## charpter 5  错误和异常

### 5.1 错误

程序员在编写程序的时候，错误往往是无法避免的，可能是因为语法用错了，也可能是拼写错了，当然还可能有其他莫名其妙的错误，比如冒号写成全角了等。总之，编程中有相当一部分就是要不停地修正错误 。

- python中的常见错误之一是语法错误，也是常见的错误。
  - 比如缺少冒号“:”(英文半角)
- 常见错误之二是在没有语法错误时，会出现逻辑错误。逻辑错误可能会由于不完整或者不合法的输入导致，也可能是无法生成、计算等，或者是其他逻辑问题。

当python检测到一错误时，解释器就无法继续执行下去，于是抛出相应的信息，这些信息我们笼统地称之为异常信息 。

### 5.2 异常

****

```python
>>>1/0
Traceback (most recent call last):
  File "<pyshell#0>", line 1, in <module>
    1/0
ZeroDivisionError: division by zero
```

当python抛出异常的时候，首先“跟踪记录（Traceback）”，还可以给它取一个更优雅的名字“回溯”，然后才显示异常的详细信息，标明异常所在位置（文件、行或某个模块）。最后一行是错误类型以及导致异常的原因。

常见的异常如表5-1所示。

|       异常        |                   描述                    |
| :---------------: | :---------------------------------------: |
|     NameError     |        尝试访问一个没有申明的变量         |
| ZeroDivisionError |                  除数为0                  |
|    SyntaxError    |                 语法错误                  |
|    IndexError     |             索引超出序列范围              |
|     KeyError      |        请求一个不存在的字典关键字         |
|      IOError      | 输入 /输出错误（比如你要读的文件不存在 ） |
|  AttributeError   |          尝试访问未知的对象属性           |

- NameError

****

```python
>>> bar
Traceback (most recent call last):
File "<stdin>", line 1, in <module>
NameError: name 'bar' is not defined
```

python中虽然不需要在使用变量之前先声明类型，但也需要对变量进行赋值，然后才能使用，不被赋值的变量，不能在python中存在，因为变量相当于一个标签，要把它贴在对象上才有意义。

- ZeroDivisionError

```python
>>>1/0
Traceback (most recent call last):
  File "<pyshell#0>", line 1, in <module>
    1/0
ZeroDivisionError: division by zero
```

- SyntaxError

****

```python
>>>for i in range(10)
SyntaxError: invalid syntax
```

这种错误发生在python代码编译的时候，当编译到这一句时，解释器不能将代码转化为python字节就报错，它是在程序运行之前出现。现在有不少编辑器都有语法校验功能，在你写代码的时候就能显示出语法的正误，这多少会对编程者有帮助。

- IndexError

****

```python
>>>a=[1,2,3]
>>>a[4]
Traceback (most recent call last):
  File "<pyshell#3>", line 1, in <module>
    a[4]
IndexError: list index out of range
```

- IOError

```python
>>>f=open('foo')
Traceback (most recent call last):
  File "<pyshell#4>", line 1, in <module>
    f=open('foo')
FileNotFoundError: [Errno 2] No such file or directory: 'foo'
```

如果你确认有文件，就一定要把路径写正确，因为你并没有告诉python要对你的computer进行全身搜查。python只会按照你指定的位置去找，找不到就异常。

- AttributeError

****

```python
>>>class A(object):
    pass
>>>a=A()
>>>a.foo
Traceback (most recent call last):
  File "<pyshell#9>", line 1, in <module>
    a.foo()
AttributeError: 'A' object has no attribute 'foo'
```

属性不存在，出现错误。

python内建的异常也不仅仅是上面几个，上面只是列出常见的异常中的几个。

在调试程序中的时候遇到了异常，不要慌张，这是好事情，是python在帮助你修改错误 。只要认真阅读异常信息，再用dir()、help()或者官方网站文档、google等来协助，一定能解决问题。

### 5.3 处理异常

在一段程序中，为了能够让程序健壮，有时候还要处理异常。

****

```python
>>>while 1:
    print('this is a division problem')
    c=input("input 'c' continue,otherwise logout:")
    if c==
    'c':
        a=input('first number:')
        b=input('second number:')
        try:
            print(float(a)/float(b))
            print('*'*20)
        except ZeroDivisionError':
            print("the second number can't be zero")
            print('*'*20)
     else:
        break            
```

```python
this is a division program.
input 'c' continue, otherwise logout:c
first number:5
second number:2
2.5
*************************
this is a division program.
input 'c' continue, otherwise logout:c
first number:5
second number:0
The second number can't be zero!
*************************
this is a division program.
input 'c' continue, otherwise logout:d
```

从运行情况来看，当在第二个数，即除数为0时，程序并没有因为这个错误而停止，而是给用户一个友好的提示，让用户有机会改正错误。这完全得益于程序中“处理异常”的设置，如果没有“处理异常”，则当异常出现时就会导致程序中止。

#### 5.3.1 try...except...

对于前述举例程序，只看try和except部分，如果没有异常发生，except子句在try语句执行之后被忽略；如果try字句中有异常发生，该部分的其他语句被忽略，直接跳到except部分，执行其后面指定的异常类型及其子句。

except后面也可以没有任何异常类型，即无异常参数。如果这样，不论Try部分发生什么异常，都会执行except。

在except子句中，可以根据异常或者别的需要，进行更多的操作。比如：

```python
>>>class Calculator(object):
    is_raise=False
    def calc(self,express):
        try:
            return eval(express)
        except ZeroDivisionError:
            if self.is_raise:
                print("zero can't be division")
            else：
                raise
```

raise，作为一个单独语句，它的含义是将异常信息抛出，并且except子句用了一个判断语句，根据不同情况确定走不同的分支。

#### 5.3.2 处理多个异常

处理多个异常并不是因为同时报出多个异常，程序在运行中，只要遇到一个异常就会有反应，所以，每次捕获到的异常一定是一个。所谓处理多个异常的意思是可以容许捕获不同的异常，由不同的except子句处理。

```python
>>>while 1:
    print('this is a division problem')
    c=input("input 'c' continue, otherwise logout")
    if c="c":
        a=input('first number:')
        b=input('second number:')
        try:
            print(a/b)
            print('*'*20)
        except ZeroDivisionError:
            print("the second number can't be zero")
        except ValueError:
            print('please input number.')
            print('*'*20)
     else:
        break
```

运行结果：

```python
this is a division problem
input 'c' continue, otherwise logoutc
first number:1
second number:'a'
Traceback (most recent call last):
  File "C:/Users/storm/Desktop/1.py", line 8, in <module>
    print(a/b)
TypeError: unsupported operand type(s) for /: 'str' and 'str'
```

如果有多个except，try里面遇到一个异常，就转到相应的except子句 ，其他的忽略。如果except没有相应的异常，该异常也会抛出，不过这时程序就要终止了，因为异常“浮出”程序顶部。

除了用多个except之外，还可以在 一个except后面放多个异常参数。比如上面的程序，可以将except部分修改为：

```python
>>>except(ZeroDivisionError,ValueError):
    print('pleasse input rightly')
    print('*'*20)
```

需要注意得是，except后面如果是多个参数，一定要用圆括号包裹起来。否则，后果自负。

在对异常的处理中，前面都是自己写一个提示语，但自己写的不如内置的异常错误提示好，如果希望把默认错误提示打印出来，但程序还不能中断，怎么办？python提供了一种方式，将上面的代码修改如下:

```python
>>>while 1:
    print('this is a division program')
    c=input("input 'c' continue, otherwise logout")
    if c=='c':
        a=input('first  input:')
        b=input('second number:')
        try:
            print(a/c)
            print('*'*20)
        except (ZeroDivision,ValueError)as e:
            print(e)
            print('*'*20)
    else:
        break
```













