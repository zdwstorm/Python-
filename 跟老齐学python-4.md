# python笔记-基本的数据类型              <sub> —storm</sub>

## charpter 4  类

类是OOP(面向对象编程)中的重要概念，也是学习Python的一个跨越。

类也是对世界的抽象结果。

### 4.1 基本概念

####  4.1.1 问题空间

问题空间是问题解决者对一个问题所达到的全部认识状态，它是由问题解决者利用问题所包含的信息和已贮存的信息主动构成的。

个问题一般从以下三个方面来定义：

- 初始状态——开始时不完全的信息或令人不满意的状况。
- 目标状态——你希望获得的信息或状态。
- 操作——为了从初始状态迈向目标状态，你可能采取的步骤。

这三个部分加在一起定义了问题空间。

#### 4.1.2 对象

对象（object），是面向对象（Object Oriented）中的术语，既表示客观世界问题空间（Namespace）中的某个具体的事物，又表示软件系统解空间中的基本元素。

Python中的一切都是对象，不管是字符串、函数、模块还是类都是对象，“万物皆对象”。

说明Python中的所有东西都能够进行拼凑组合应用，因为对象就是可以拼凑组合应用的。

- 对象：一个对象有自己的状态、行为和唯一的标识；所有相同类型的对象所具有的结构和行为在它们共同的类中被定义。
- 状态（state）：包括这个对象已有的属性（通常是类里面已经定义好的）和对象具有的当前属性值（这些属性往往是动态的）。
- 行为（behavior）：是指一个对象如何影响外界及被外界影响，表现为对象自身状态的改变和信息的传递。
- 标识（identity）：是指一个对象所具有的区别于所有其他对象的属性（本质上指内存中所创建的对象的地址）。

简化之，对象应该具有属性（就是上面的状态，因为属性更常用）、方法（就是上面的行为，方法常被使用）和标识。因为标识是内存中自动完成的，所以，平时不用怎么管理它，主要就是属性和方。

任何一个对象都要包括这两部分：属性（是什么）和方法（能做什么）。

#### 4.1.3 面向对象

面向对象程序设计（英语：Object-oriented programming，缩写：OOP）是一种程序设计范型，同时也是一种程序开发的方法。对象指的是类的实例，它将对象作为程序的基本单元，将程序和数据封装其中，以提高软件的重用性、灵活性和扩展性。
面向对象程序设计可以看作是一种在程序中包含各种独立而又互相调用的对象的思想，这与传统的思想刚好相反：传统的程序设计主张将程序看作是一系列函数的集合，或者直接就是一系列对电脑下达的指令。面向对象程序设计中的每一个对象都应该能够接受数据、处理数据并将数据传达给其他对象，因此它们都可以被看作是一个小型的“机器”，即对象。
目前已经被证实的是，面向对象程序设计推广了程序的灵活性和可维护性，并且在大型项目设计中广为应用。此外，支持者声称面向对象程序设计要比以往的做法更加便于学习，因为它能够让人们更简单地设计并维护程序，使得程序更加便于分析、设计、理解。反对者在某些领域对此予以否认。
当我们提到面向对象的时候，它不仅指一种程序设计方法，更多意义上是一种程序开发方式。在这一方面，我们必须了解更多关于面向对象系统分析和面向对象设计（Object Oriented Design，简称OOD）方面的知识。

#### 4.1.4 类 

在面向对象程序设计中，类（class）是一种面向对象计算机编程语言的构造，是创建对象的蓝图，描述了所创建的对象共同的属性和方法。

类的更严格的定义是由某种特定的元数据所组成的内聚的包。它描述了一些对象的行为规则，而这些对象就被称为该类的实例。类有接口和结构。接口描述了如何通过方法与类及其实例互操作，而结构描述了一个实例中数据如何划分为多个属性。类是与某个层的对象的最具体的类型。类还可以有运行时表示形式（元对象），它为操作与类相关的元数据提供了运行时支持。
支持类的编程语言在支持与类相关的各种特性方面都多多少少有一些微妙的差。大多数都支持不同形式的类继承。许多语言还支持提供封装性的特性，比如访问修饰符。类的出现，为面向对象编程的三个最重要的特性（封装性、继承性、多态）提供了 的手段。

#### 4.1.5 编写类

类是对某一群具有同样属性和方法的对象的抽象。

要定义类，就要抽象，找出共同的方面。

****

class 美女：  #用class来声明，后面定义的是一个类

​			pass

****

****

class 美女：

​		胸围=90

​		腰围=58

​		臀围=83

​		皮肤=white

​		唱歌()

​		做饭()

****

上述例子定义了一个名称为“美女”的类，其中约定，没有括号的是属性，有括号的是方法。

`王美女=美女() #类的具体化就是实例`

****

`a=王美女.胸围`

用点号“.”的方式，表示王美女的胸围，得到的变量a就是90。另外，还可以通过这种方式给属性赋值，比如，

`王美女.皮肤=black`

通过实例，也可以访问某个方法，比如，

`王美女.做饭（）`

### 4.2 详解类

#### 4.2.1 新式类和旧式类

>因为Python是一个不断发展的高级语言，导致了在Python 2.x的版本中，有“新式类”和“旧式类（也叫做经典类）”之分。新式类是Python 2.2引进的，在此后的版本中，我们一般用的都是新式类。本着知其然还要知其所以然的目的，简单回顾一下两者的别。

```python
>>>class AA:
    pass
```

这定义了一个非常简单的类，而且是旧式类。

`>>> aa=AA() #将类实例化`

```python
>>> type(AA)
<type 'classobj'>
>>> aa.__class__
<class __main__.AA at 0xb71f017c>
>>> type(aa)
<type 'instance'>
```

解读一下上面的含义。

- type（AA）：查看类AA的类型，返回的是'classobj'。

- aa.__class__：==aa是一个实例，也是一个对象，每个对象都有__class__属性==，用于显示它的类型。这里返回的结果是，从这个结果中可以读出的信息是，aa是类AA的实例，并且类AA在内存中的地址是0xb71f017c。

- type（aa）：是要看实例aa的类型，它显示的结果是instance，意思是告诉我们它的
  类型是一个实例。

  新式类如下：

  ****

  ```python
  >>>class bb(object):
      pass
  >>>B=bb()
  >>>B._class_
  <class '__main__.bb'>
  >>>type(B)
  <class '__main__.bb'>
  ```

  新式类和旧式类还在于两者对于多重继承的查找和调用的方式不同，旧式类是深度优先，新式类是广度优先。

  不管是新式类还是旧式类，都可以通过如下的方法查看它们在内存中的存储空间信息。

  ```python
  >>>print(B)
  <__main__.bb object at 0x00000144A5BF83C8>
  ```

  新式类和旧式类的差别在于类的名字后面要跟上（object），这其实是一种名为“继承”的类的操作，当前的类BB是以类object为上级的（object被称为父类），即BB是继承自类object的新类。在python3中，所有的类自然地都是类object的子类。

  ```python
  >>>class BB(object)： #第一种新式类的定义方法
  	pass
  ```

  第二种定义方法，在类的前面写上：`_metaclass_=type`，然后定义类的时候，就不需要在名字后面写（object）了。

  ```python
  >>>_metaclass_type
  >>>class  CC:
      pass
  >>>cc=CC()
  >>>cc._class_
  <class '__main__.cc'>
  ```

  #### 4.2.2 创建类 

  在一般情况下，一个类不是两三行就能搞定的，所以，下面可能很少使用交互模式了 ，因为那样一旦有一点错误就前功尽弃 了，下面改用编辑页面。

  ****

  class person(object):

  ​	def `__init__`(self,name):

  ​		self.name=name

  ​	def  getName(self):

  ​		return self.name

  ​	def color(self,color):

  ​		print('{} is {}'.format(self.name,color))

  ****

  对上面定义的类进行解释：

  1. 定义类

  class Person，这是在声明创建一个名为“Person”的类。类的名称一般用大写字母开头，这是惯例。如果名称是两个单词，那么两个单词的首字母 都要大写，例如class HotPerson，这种命名方法有一个形象的名字，叫作“驼峰命名”。当然，如果故意不遵循此例，也未尝不可。

  以缩进表示的就是这个类的内容了。其实那些东西看起来并不陌生—就是已经学习过的函数。不过 ，很多程序员喜欢把类里面的函数叫作方法，就是上节中说到的对象的方法。

  函数的命名方法是以def发起，并且函数名称首字母不要用大写，可以使用aa_bb的样式，也可以使用aaBb的样式，一切看你的习惯了。

  ==类中的函数（方法）的参数跟以往的参数样式有区别，那就是每个函数必须包括self函数，并且作为默认的第一个参数，这是需要注意的地方。==至于它的用途，继续学习即可知道。

  2. 初始化

  def_init_这个函数比较特殊，并且有一个名字，叫作初始化函数（注意，很多教材和资料中都把它叫作构造函数）。它是以两个下划线开始，然后以两个下划线结束。
  
  所谓初始化，就是让类有一个基本的面貌。做很多事情都要初始化，让事情有一个具体的起点状态。在类被实例化的时候就执行这个函数，从而将初始化的一些属性可以放到这个函数里面。
  
  此例中的初始化函数就意味着实例化的时候，要给参数name提供一个值，作为类初始化的内容。就是在这个类被实例化的同时，要通过name参数传递一个值，这个值一开始就被写入类和实例中，称为类和实例的一个属性。
  
  `girl=Person('canglaoshi')`

girl就是一个实例对象，它有属性和方法，这里仅说属性，当通过上面的方式实例化后，就自动执行了初始化函数，让实例girl就具有了name属性。

```python
>>>print(girl.name)
```

这就是初始化的功能，简而言之，通过初始化函数，确定了这个实例（类）的“基本属性”。

初始化函数就是一个函数，所以，它的参数设置也符合前面学过的函数参数设置规范。比如：

****

```python
def __init__(self,*args):
    pass
```

------

这种类型的函数*args和前面讲述的函数参数一样，self这个参数是必须要有的。

很多时候，并不是每次都要从外面传入数据，有时候会把初始化函数的某些参数设置默认值，如果没有新的数据传入，就应用 这些默认值。

****

```python
>>>class Person:
    def __init__(self,name,lang='golang',website='www.google.com'):
        self.name=name
        self.lang=lang
        self.website=website
        self.email='1044857432@qq.com'
<<<laoqi=Person('laoqi')
>>>info=Person('qiwsir',lang='python',website='qiweisir.github.io')
>>>print('laoqi.name=',laoqi.name)
>>>print('info.name=',info.name)
>>>print('-'*10)
>>>print('laoqi.lang=',laoqi.lang)
>>>print('-'*10)
>>>print('laoqi.website=',laoqi.website)
>>>print('info.websie',info.website)        
```

运行结果

```python
laoqi.name= LaoQi
info.name= qiwsir
-------
laoqi.lang= golang
info.lang= python
-------
laoqi.website= www.google.com
info.website= qiwsir.github.io
```

在编程界有这样一句话：“类是实例工厂”，什么意思呢？生产物品，比如生产电脑，一个工厂可以生产好多电脑，那么，类就能“生产”好多实例，所以，它是“工厂”。比如上面例子中，就有两个实例。

#### 4.2.3 类中的函数（方法）

这里的‘函数’，指的是类中的那些函数，也把它叫作“方法”。

```
class person(object):

​	def `__init__`(self,name):

​		self.name=name

​	def  getName(self):

​		return self.name

​	def color(self,color):

​		print('{} is {}'.format(self.name,color))
```

构造函数（初始化函数）的后面有两个函数：def .getName(self)和def color(self,color)，这两个函数和前面的初始化函数有共同的地方，都是以self作为第一个参数。

****

```python
>>>def getName(self):
    return self.name
```

****

这个函数的作用就是返回在初始化时得到的值，初始化函数中self.name的值能够在这个函数中被使用，其原因就在于此函数中不可缺少的参数self。

****

```python
>>>girl=Person('canglaoshi')
>>>name=girl.getName()
```

girl.getName()就是调用实例girl的getName()方法（函数）。调用该方法的时候要特别注意，方法名后面的括号必不可少 ，并且括号中不要写参数，在类中的getName(self)函数的第一个参数self是默认的，当实例化之后，调用此函数的时候，第一个参数不需要赋值，那么，变量name的最终结果就是nname='canglaoshi'。

同样道理，对于方法：

****

```python
>>>def color(self,color):
    print('{} is {}'.format(self.name,color))
```

也是在实例化之后调用：

****

```python
>>>girl.color('white')
```

这也是在执行实例化方法，只是由于类中的该方法有两个参数，除了默认的self之外，还有一个color,所以，在调用这个方法的时候，要为后面那个参数传值。

#### 4.2.4 类和实例

- “类提供默认行为，是实例的工厂”，这句话非常经典，一下道破了类和实例的关系。所谓工厂，就是可以用同一个模子做出很多具体的产品，类就是那么模子，实例就是具体的产品。所以，实例是程序处理的实际对象。
- 类由一些语句组成，但是实例通过调用类生成，每次调用这个类，就得到这个类的新的实例。
- 命名类必须用class，例如class Person。class 发起了一个可执行的语句，如果执行，就得到一个 类对象，并且将这个类对象赋值给对象名（比如Person)。

#### 4.2.5 self的作用

类里面的函数，第一个参数就是self，而且不能省略。但是在实例化的时候，这个参数不需要写，也不需要为这个参数传值，似乎就没有这个参数什么事了。

self是一个很神奇的参数。

以前面的类“Persnon"为例，在Person实例化的过程中，girl=Person('canglaoshi')，字符串’canglaoshi‘通过初始化函数（`__init__()`）的参数已经存入到内存中，并且以Person类型的面貌存在，组成了一个对象，这个对象和变量girl建立起引用关系。这个过程也可说成这些数据附加到一个实例上。这样就能够以object.attribute的形式存在，在程序任何地方调用某个对象（数据）。例如上面的程序中以girl.name的方式得到'canglaoshi'。这种调用方式，在类和实例中经常使用，点号“.”后面的称之为类或者实例的属性。

在类内部，就是将所有传入的数据都赋给一个变量，通常这个变量的名字是self。注意，这是习惯，而且是共识，所以，你就不要费尽心思另外取别的名字了。

在初始化函数中的第一个参数self就是起到了这个作用—接收实例化过程中传入的所有数据，这些数据是初始化函数的参数导入的。显然，self应该就是一个实例（准确来说是应用实例），因为它所对应的就是具体数据。

****

```python
>>>class Person(object):
    def__init__(self,name):
        self.name=name
        print(self)
        print(type(self))
>>>girl=Person('canglaoshi')
<__main__.Person object at 0x0000027209257128> #证实self就是一个实例对象
<class '__main__.Person'>
```

self这个实例跟前面说的那个girl所引用的实例对象一样，也有属性。那么，接下来就规定其属性和属性对应的数据。上面代码中，self.name=name,就是规定了self实例的一个属性，这个属性的名字叫做name，且属性的值等于初始化函数的参数name所导入的数据。注意，self.name中的name和初始化函数的参数name没有任何关系，它们两个一样，只不过是一种巧合。如果，写成self.xya=name也是可以的。

其实，从效果的角度来理解更简化：类的实例girl对应self，girl通过self导入实例属性的所有数据。

当然，self的属性数据，也不一定非得由参数传入，也可以在构造函数中自己设定。

比如：

```python
>>>class Person():
    def__init__(self,name):
        self.name=name
        self.email="1044957332@qq.com" #这个属性不是通过参数传入的 
>>>info=Person("qiwsir")
>>>print("info.name=",'info.name')
>>>print('info.email=','info.email')
```

运行结果

****

```python
info.name= qiwsir
info.email= qiwsir@gmail.com #打印结果
```

这个例子让我们拓展了对self的认识，它不仅仅是为了在类内部传递参数导入的数据，还能在初始化函数中，通过self.attribute的方式，规定self实例对象的属性，这个属性也是类实例化对象的属性，即作为类通过初始化函数初始化后所具有的属性。所以在实例info中，通过info.email同样能够得到该属性的数据。在这里，就可以把self形象地理解为“内外兼修”了。或者按照前面所提到的，将info和self对应起来，self主内、info主外。

#### 4.2.6 文档字符串

本书中已经强调过写注释的重要性了，同样，在类里面也要写点东西。

在函数里面，里面可以用三重引号来写说明，在类中也可以，其实在文件开头的部分也能用三重引号写文档字符串说明。这样写的最大好处是能够用help()函数看。

****

```python
'''This is python lesson'''
>>>def start_func(arg):
    '''this is a function'''
    pass
>>>class Myclass:
    '''this is my class'''
    def my_method(self.arg):
        '''this is my method'''
        pass
```

这样的文档不是必需的，当然，在编程中，有不少地方要用"#"符号来做注释。

### 4.3 辨析有关概念 

#### 4.3.1 类属性和实例属性

一个类实例化以后，实例就是一个对象，它有属性。python的类也是一个对象，且也有属性。所以就有了“类属性”和“实例属性”两个属性。

****

```python
>>>class A(object):
    x=7
>>>A.X
7
```

在类A中，变量x所引用的对象，能够直接类调用。或者说x是类A的属性，这就是所谓的“类属性”。类属性仅限于此—类中的变量还有另外的称呼，如静态数据。

****

```python
>>>foo=A()
>>>foo.x
7
```

将类A实例化，通过实例foo也可以得到属性（foo.x），这个属性叫作“实例属性”。

对于同一属性，可以用类来访问（类属性），在一般情况下，也可以通过实例来访问同样的属性。

但有时候它们有区别。相同的地方好理解，关键是区别才是编程中要注意之处。

****

```
>>>foo.x+=1
>>>foo.x
8
>>>A.x
7
```

实例属性（foo.x）更新了，类属性（A.x）没有改变。这至少说明，类属性不会被实例属性左右，也可以进一步说明“类属性与实例属性无关”（这句话不能理解为“类属性”和“实例属性”互不相关，如果要这么理解，按照更严格的逻辑，应该还要看看修改的A.x变化是否影响到foo.x）。

foo.x+=1的本质是实例foo又建立了一个新的属性，但是这个属性（新的foo.x）居然与原来的属性（旧的foo.x）重名，所以，原来的foo.x就被“遮盖”了，只能访问到新的foo.x，它的值是8。既然新的foo.x“遮盖”了旧的foo.x，如果删除它，旧的就会显现出来。

****

```python
>>>foo.x
8
>>>del foo.x
>>>foo.x
7
```

此外，还可以通过建立一个不与旧的实例属性重名的实例属性，理解上述过程。

****

```python
>>>foo.y=foo.x+1
>>>foo.y
8
>>>foo.x
7
```

foo.y就是新建的一个实例属性，它没有影响原来的实例属性foo.x。

前面看到了实例属性不左右类属性，反过来，类属性能否影响实例属性呢？实例就是通过实例化类实现的，按照推理，实例属性应该受到类属性的影响。

```python
>>>A.x+=1
>>>A.x
8
>>>foo.x
8
```

实例属性的值随着类属性的值变化而变化了。

综上，“类属性不受实例属性影响，但实例属性受到类属性左右”，不过，这个结论是有条件的，前面例子中类内的变量应用的是不可变对象（整数）。根据对可变对象和不可变对象的研究经验（可参考浅拷贝和深拷贝），按照保守主义的原则，还应考虑对象是可变对象的情形，因为可变数据能够进行原地修改，这可能会导致不一样。

****

```python
>>>class B(object):
    y=[1,2,3]
>>>B.y
[1,2,3]
>>>bar=B()
>>>bar.y
[1,2,3]
>>>bar.y.append(4)
>>>bar.y
[1,2,3,4]
>>>B.y
[1,2,3,4] #类属性此时也发生了变化
>>>B.y.append('aa')
>>>B.y
[1,2,3,4,'aa']
>>>bar.y
[1,2,3,4,'aa']
```

当类中变量引用的是可变对象时，类属性和实例属性都能直接修改这个对象，从而影响另一方的值。

```python
>>>foo=A()
>>>dir(foo) #实例化A，可以查看其所有的属性
```

增加一个类属性，同时在实例属性中也增加了一样的名称和数据的属性。

```python
>>>A.y='python'
>>>foo.y
'python'
```

反过来，增加实例属性，会不会也增加了一个类属性呢？

```python
>>> foo.z = "python"
>>> foo.z
'python'
>>> A.z
Traceback (most recent call last):
File "<stdin>", line 1, in <module>
AttributeError: type object 'A' has no attribute 'z'
```

类并没有收纳通过实例增加的这个属性，这进一步说明，类属性不受实例属性左右。

不管是通过类，还是通过实例，都可以增加和修改属性，其方法就是通过类或者实例的点号操作来实现，即object.attribute，可以实现对属性的修改和增加。

#### 4.3.2  数据流转

在类的应用中，最广泛的是将类实例化，通过实例来执行各种方法（即类里面的函数）。所以，对此过程中的数据流转一定要弄明白。

```python
>>>class Person(object):
    def __init__(self,name):
        self.name=name
    def getName(self):
        return self.name
    def breast(self,n):
        self.breast=n
    def color(self,color):
        print("{} is {}".format(self.name,color))
    def how(self):
        print('{} breast is {}'.format(self.name,self.breast))
>>>girl=Person('canglaoshi')
>>>girl.breast(90)
>>>girl.color('white')
>>>girl.how()
```

运行结果

```python
canglaoshi is white
canglaoshi breast is 90
```

![截图20190522073332](C:\Users\storm\Desktop\截图20190522073332.png)

创建实例girl=Person('canglaoshi')，注意观察图上的箭头方向。girl这个实例和Person类中的self对应，这正是应了上节所概括的“实例变量与self对应，实例变量主外，self主内”的结论。“canglaoshi”是一个具体的数据，通过初始化函数中的name参数，传给self.name，你应已知self也是一个实例，可以为它设置属性，self.name就是一个属性，经过初始化函数，这个属性的值由参数name传入，现在就是“canglaoshi”。

在类person的其他方法中，都是以self为第一个或唯一一个参数。注意，在python中，这个参数要显明写上，在类内部的函数的参数是不能省略的。这就表示所有python方法都继承self实例对象，它的属性也被带到每个函数中。例如在其他函数里面使用self.name即是调用前面已经确定的实例属性参数。当然，在函数中，还可以继续为实例self增加属性，比如self.breast。这样，通过self实例，就实现了数据在类内部的流转。

如果要把数据从类里面传到外面，可以通过return语句实现。如上述例子中所表示的getName方法。

实例名称girl和self是对应关系，实际上，在类里面也可以用girl代替self。例如，做如下的修改：

```python
>>>class Person(object):
    def __init__(self,name):
        self.name=name
    def getName(self):
       # return self.name
         return girl.name #修改成这样，但是在实际编程实践中不要这么做。
>>>girl=Person('canglaoshi')
>>>name=girl.getName()
>>>print(name)
```

运行结果：

`canglaoshi`

这个例子说明，在实例化之后，实例变量girl和函数里面的self实例是完全对应的。但是，千万不要用上面修改的方式，因为那样写使类没有独立性，这是大忌。

#### 4.3.3 命名空间

命名空间（namespaces），在研究类或者面向对象编程中，它常常被提到。虽然在函数那部分已经对命名空间有初步解释，但那是在函数的知识范畴中的理解。现在，我们在类的知识范畴中理解“类命名空间”——定义类时，所有位于class语句中的代码都在某个命名空间中执行，即类命名空间。

命名空间是从所定义的命名到对象的映射集合。

不同的命名空间可以同时存在，彼此相互独立互不干扰。

命名空间因为对象的不同也有所区别，可以分为如下几种。

- 内置命名空间：python运行起来 ，它们就存在了。内置函数的命名空间都属于内置命名空间，所以，我们可以在任何程序中直接运行它们，比如前面的id()，不需要做什么操作，拿过来就能直接使用。
- 全局命名空间：每个模块创建它自己所拥有的全局命名空间，不同模块的全局命名空间彼此独立，不同模块中相同名称的命名空间，也会因为模块的不同而不相互干扰。
- 本地命名空间：模块中有函数或者类，每个函数或者类所定义的命名空间就是本地命名空间。如果函数返回了结果或者抛出异常，则本地命名空间也就结束了。

==程序在查询上述三种命名空间的时候，按照从里到外的顺序，即：LocalNamespaces→Global Namesspaces→Built-in Namesspaces。==

```python
>>>def foo(num,str):
    name='world'
    print locals()
>>>foo(221,'python')
{'num':221,'name':'world','str':'python'}
```

![截图20190522220541](C:\Users\storm\Desktop\截图20190522220541.png)

这是一个访问本地命名空间的方法，用print locals()完成，从这个结果中不难看出，所谓的命名空间中的数据存储结构和dictionary是一样的。

根据习惯，如果访问全局命名空间，可以使用print globals()。

#### 4.3.4 作用域 

作用域是指python程序可以直接访问到的命名空间。“直接访问”在这里意味着访问命名空间的命名时无须加入附加的修饰符。

程序也是按照搜索命名空间的顺序，搜索相应空间的能够访问到的作用域。

```python
>>>def outer_foo():
    b=20
    def inner_foo():
        c=30
>>>a=10        
```

假如我现在位于inner_foo()函数内，那么c对我来讲就在本地作用域，而b和a就不是。如果我在inner_foo()内再做：b=50，这其实是在本地命名空间内新创建了对象，和上一层中的b=20毫不相干。可以看下面的例子：

```python
>>>def outer_foo():
    a=10
    def inner_foo():
        a=20
        print('inner_foo,a=',a) #a=20
    inner_foo()
    print('outer_foo,a=',a) #a=10
>>>a=30
>>>outer_foo()
>>>print('a=',a) #a=30   
```

运行结果：

```python
inner_foo, a= 20
outer_foo, a= 10
a= 30
```

如果要将某个变量在任何地方都使用，且能够关联，那么在函数内就使用global声，其实就是曾经讲过的全局变量。

### 4.4 继承

继承是面向对象软件技术中的一个概念。如果一个类别A“继承”自另一个类别B，则把这个A称为"B的子类别"，而把B称为“A的父类别”，也可以称“B是A的超类”。

继承可以使得子类别具有父类别的各种属性和方法，而不需要再次编写相同的代码。在令子类别继承父类别的同时，可以重新定义某些属性，并重写某些方法，即覆盖父类别的原有属性和方法，使其获得与父类别不同的功能。另外，为子类别追加新的属性和方法也是常见的做法。

继承的意图（好处）：

（1）可以实现代码重用，但不仅仅是实现代码重用，有时候根本就没有重用。

（2）实现属性和方法继承。

从技术上说，OOP里继承最主要的用途是实现多态。对于多态而言，重要的是接口继承性，属性和行为是否存在继承性，这是不一定的。事实上，大量工程实践表明，重度的行为继承会导致系统过度复杂和臃肿，反而会降低灵活性。因此现在比较提倡的是基于接口的轻度继承理念。这种模型里因为父类（接口类）完全没有代码，因此根本谈不上什么代码复用。

在python里，因为存在Duck Type ，接口定义的重要性大大降低，继承的作用也进一步被削弱了。

#### 4.4.1基本概念

****

````python
>>>class Person(object):
    def speak(self):
        print("I love you")
    def SetHeight(self):
        print（"the height is: 1.60m"）
    def breast(self,n):
        print("my breast is:",n)
>>>class Girl(person):
    def SetHeight(self):
        print("the height is: 1.70m")
>>>cang=Girl()
>>>cang.SetHeight()
>>>cang.Speak()
>>>cang.breast(90)
````

运行结果：

****

the height is : 1.70m

i love you

my breast is: 90

****

对以上程序进行解释：

首先定义了 一个类Person，在这个类中定义了三个方法。注意，没有定义初始化函数，初始化函数在类中不是必须的。

然后又定义了一个类Girl，这个类的名字后面的括号中是上一个类的名字，这就意味着Girl继承了Person，Girl是Person的子类，Person是Girl的父类。

既然是继承了Person，那么Girl就拥有了Person中的全部方法和属性。但是，如果Gril里面有一个和Person同样名称的方法，那么就把Person中的同一个方法遮盖住了，显示的是Girl中的方法，这叫方法的重写。实例化类girl之后，执行实例方法cang.setHeight()，由于在类girl中重写了setHeight方法，那么Person中的那个方法就不显作用了，在这个实例方法中执行的是类girl中的setHeight方法。

#### 4.4.2 多重继承

所谓多重继承就是指某一个类所继承的父类，不止一个，而是多个。比如：

****

```python
>>>class person(object):
    def eye(self):
        print('two eyes')
    def breast(self,n):
        print('the breast is:',n)
>>>class girl(object):
    age=28
    def  color(self):
        print('the girl is white')
>>>class hotgilr(person,girl):
    pass
>>>kong=hotgirl()
>>>kong.eye()
>>>kong.breast(90)
>>>kong.color()
>>>print(kong.age
```

运行结果：

在这个程序中，前面有两个类：person和girl，然后第三个类hotgirl继承了这两个类 。

实例化hotgirl，既然继承了上面的两个类，那么那两个类的方法就都能够拿过来使用。保存程序，运行一下看看：

****

The breast is: 90
The girl is white
28

****

值得注意的是，在类girl中，有一个age，在对hotgirl实例化之后，因为继承的原因，这个类属性也被继承到hotgirl中，因此通过实例化属性kong.age一样能得到该数据。

#### 4.4.3 多重继承的顺序

学习多重继承的顺序很有必要。比如，如果一个类继承了两个父类，并且两个父类有同样的方法或者属性，那么在实例化子类后，调用哪个父类的方法和属性呢？

****

```python
>>>class k1(object):
    def foo(self):
        print('k1-foo')
>>>class k2(object):
    def foo(self):
        print('k2-foo')
    def bar(self):
        print('k2-bar')
>>>class j1(k1,k2):
    pass
>>>class j2(k1,k2):
    def bar(self):
        print('j2-bar')
>>>class c(j1,j2):
    pass
>>>print(c._mro_)
>>>m=c()
>>>m.foo()
>>>m.bar()    
```

代码中的`print(c._mro_)`是要打印出类的继承顺序。如果要执行foo()方法，首先看J1，没有的，看j2，还没有，看j1里面的k1，有了就执行，即c==>j1==>j2==>k1；bar也是按照这个顺序，在j2中就找到了一个。

这种对继承属性和方法的搜索的顺序称之为“广大优先”。

#### 4.4.4 super 函数

初始化函数的继承跟一般方法的继承还有点不同，可以看下面的例子：

****

```python
>>>class person(object):
    def __init__(self):
        self.height=160
    def about(self,name):
        print('{} is about（）'.format(name,self.height))
>>>class Girl(person):
    def __init__(self):
        self.breast=90
    def about(self,name):
        print('{} is a hot girl,she is about（）,and her breast \is{}'.format(name,self.height,self.breast))
>>>cang=Girl()
>>>cang.about('canglaoshi')
Traceback (most recent call last):
  File "C:/Users/storm/Desktop/1.py", line 12, in <module>
    cang.about('canglaoshi')
  File "C:/Users/storm/Desktop/1.py", line 10, in about
    print('{} is a hot girl,she is about（）,and her breast \is{}'.format(name,self.height,self.breast))
AttributeError: 'Girl' object has no attribute 'height'     
```

==不求最好，但求报错。==

报错信息显示，self.height是不存在的，也就是说类girl没有从person中继承过来这个属性。

仔细观察girl会发现，除了刚才强调的about方法重写了，`_init_`方法也被重写了，不要觉得它的名字模样奇怪，就不把它看做类中的方法（函数），它跟person中的`_init_`重名了，同样是重写了初始化函数，而gril中的`_init_`中根本就没有关于self.height的任何信息。

子类中重写了父类的某个方法后，父类中同样的方法就被覆盖了。

```python
>>>class person(object):
    def __init__(self):
        self.height=160
    def about(self,name)：
         print('{} is about {}'.format(name,self.height))
>>>class girl(person):
    def __init__(self):
        super(girl,self).__int__()
        self.breast=90
    def about(self,name):
        print('{} is a hot girl,she is about（）,and her breast \is{}'.format(name,self.height,self.breast))
        super(girl,self).about(name)
>>>cang=girl()
>>>cang.about('canglaoshi')        
```

在子类中，`_init_`方法重写了，为了调用父类同方法，使用super(girl,self).`_init_`的方式。super函数的参数，第一个是当前子类的类名字，第二个是self，然后是点号，点号后面是所要调用的父类的方法。同样在子类重写的about方法中，也可以调用父类的about方法。

### 4.5 方法

在程序中，最常见的是实例化类 ，通过实例来调用类的方法，对以往的经验稍作概括：

- 方法是类内部定义的函数，只不过这个函数的第一个参数是self(可以认为方法是类属性，但不是实例属性)。
- 必须将类实例化之后，才能通过实例调用该类的方法。调用的时候在方法后面要有括号（括号中默认有self参数，但是不写出来）。

通过实例调用方法，我们称这个方法绑定到实例上。

#### 4.5.1 绑定方法

调用绑定方法，其实一直在这样做，司空见惯。比如：

****

```python
>>>class Person(object):
    def foo(self):
        pass
```

如果要调用Person.foo()方法，必须 ：

****

```python
>>>pp=Person() #实例化
>>>pp.foo()
```

这样就实现了方法和实例的绑定，于是通过pp.foo()即可调用该方法。

#### 4.5.2 非绑定方法

```python
>>>class person(object):
    def __init__(self):
        self.height=160
    def about(self,name)：
         print('{} is about {}'.format(name,self.height))
>>>class girl(person):
    def __init___(self):
        super(girl,self).__int__()
        self.breast=90
    def about(self,name):
        print('{} is a hot girl,she is about（）,and her breast \is{}'.format(name,self.height,self.breast))
        super(girl,self).about(name)
>>>cang=girl()
>>>cang.about('canglaoshi')        
```

在子类girl中，因为重写了父类的`_init_`方法，如果要调用父类该方法，不得不使用super(girl，self).`_init_`调用父类中因为子类方法重写而被遮盖的同名方法。

在子类中，父类的方法就是非绑定方法，因为在子类中，没有建立父类的实例，却用父类的方法。对于这种非绑定方法的调用，还有一种方式，但现在已经较少使用了，因为有了super函数，为了方便读者看其他代码，还是要简单说明一下。

例如在上面的代码中，在类girl中想调用父类Person的初始化函数，则需要在子类中写上这么一行：

`Person.__init__(self)`

这不是通过实例调用的，而是通过类Person实现了对`_init_(self)`的调用。这就是调用非绑定方法的用途。推荐使用super函数。

#### 4.5.3 静态方法和类方法

类的方法第一个参数必须是self，并且如果要调用类的方法，要通过类的实例，即方法绑定实例后才能由实例调用。如果不绑定，一般在继承关系的类之间，可以用super函数等方法调用。

```python
>>>class staticmethod(object):
    @staticmethod
    def foo():
        print('this is static method foo()')
>>>class classmethod(object):
    @classmethod
    def bar(cls):
        print('this is class method bar()')
        print('bar() is part of class',cls._name_)
>>>static_foo=staticmethod() #实例化
>>>static_foo.foo() #实例调用静态方法
>>>staticmethod.foo()#通过类调用静态方法
>>>print('*'*10)
>>>class_bar=classmethod()
>>>class_bar.bar()
>>>classmethod.bar()
```

对于这部分代码，有一处非常特别，那就是包含了'@'符号。在python中：

- @staticmetod表示下面的方法是静态方法。
- @classmethod表示下面的方法是类方法。

先看静态方法，虽然名为静态方法，但也是方法，所以，依然用def语句来定义。需要注意的是文件名后面的括号里面没有self，这和前面定义的类中的方法不同，也正是因为这个不同，才给它另外取了一个名字叫静态方法。

再看类方法，同样也具有一般方法的特点，区别也在参数上，类方法的参数也没有self，但是必须有cls这个参数。在类方法中，能够访问类属性，但是不能访问实例属性。

这两种方法都可以通过实例调用，即绑定实例。也可以通过类来调用，即staticmethod.foo()这样的形式，这也是区别一般方法的地方，一般方法必须通过绑定实例调用。

上述代码运行结果：

****

This is static method foo().
This is static method foo().

`*************`

This is class method bar().
bar() is part of class: ClassMethod
This is class method bar().
bar() is part of class: ClassMethod

****

### 4.6 多态和封装

#### 4.6.1 多态

```python
>>>'this is a book'.count('s')
2
>>>[1,2,3,4,5,3].count(3)
2
```

count函数的作用是数一数某个元素在对象中出现的次数。从例子中可以看出，python并没与限定count的参数所引入的值应该是什么类型的。

````python
>>>f=lambda x,y:x+y
>>>f(2,3)
f
>>>f('wold','python')
'woldpython'
>>>f(['python','java'],['c++','lisp'])
['python','java','c++','lisp']
````

同样，在lambda函数中，python同样没有限制应该传入什么样的对象（或者说数据，值）。也就是说，允许给参数传任意类型的数据，并返回相应的结果 ，至于是否报错，则取决于“+”的能力范围。这就是“多态”的体现。

“多态”能否正确表达，不是通过限制传入的对象类型实现，而是这样处理：

```python
>>>f('a',1)
Traceback (most recent call last):
  File "<pyshell#1>", line 1, in <module>
    f('a',1)
  File "<pyshell#0>", line 1, in <lambda>
    f=lambda x,y:x+y
TypeError: can only concatenate str (not "int") to str
```

在这个例子中，把判断两个对象是否能够相加的任务交给了“+”，不是放在入口处判断类型是否为字符串或者数字。

多态，是指面向对象程序执行时，相同的信息可能会送给多个不同的类别对象，系统可依据对象所属类别，引发对应类别的方法而有不同的行为。简单来说，所谓多态意指相同的信息给与不同的对象会引发不同的动作。

简化的说法就是“有多种形式”，就算不知道变量（参数）所引用的对象类型，也一样能进行操作，来者不拒。

著名的repr()函数，它能够针对输入的任何对象返回一个字符串，这就是多态的代表之一。

```python
>>>repr([1,2,3])
'[1,2,3]'
>>>repr(1)
'1'
```

```python
>>>def length(x):
    print('the length of',repr(x),'is',len(x))
>>>length('how are you')
the length of 'how are you' is 11.
```

下面情况会报错：

```python
>>>length(7)
Traceback (most recent call last):
  File "<pyshell#6>", line 1, in <module>
    length(7)
  File "<pyshell#2>", line 2, in length
    print('the length of',repr(x),'is',len(x) )
TypeError: object of type 'int' has no len()
```

"猫和狗"

```python
>>>class animal(object):
    def __init__(self,name=''):
        self.name=name
    def  talk(self):
        pass
>>>class cat(animal):
    def talk(self):
        print('meow')
>>>class dog(animal):
    def talk(self):
        print("woof")
>>>a=aniaml()
>>>a.talk
>>>c=cat('missy')
>>>c.talk()
>>>d=dog('rocky')
>>>d.talk()
```

```python
meow
woof
```

代码中有cat和dog两个类，都继承了类animal，它们都有talk()方法，输入不同的动物名称，会得出相应的结果。

#### 4.6.2 封装和私有化

在程序设计中，封装是对对象的一种抽象，即将某些部分隐藏起来，在程序外部看不到，无法调用。

私有化：就是将类或者函数中的某些属性限制在某个区域之内，外部无法调用。

python中的私有化的方法也比较简单，就是在准备私有化的属性（包括方法，数据）名字前面加双下划线。

例如 ：

****

```python
>>>class protectme(object):
    def __init__(self):
        self.me='deng'
        self.__name='wen'
    def python(self):
        print('i love python')
    def code(self):
        print('which language do you like')
        self.__python()
>>>p=protectme()
>>>print(p.me)
>>>print(p.__name)
```

```python
deng
Traceback (most recent call last):
  File "C:/Users/storm/Desktop/1.py", line 12, in <module>
    print(p.__me)
AttributeError: 'protectme' object has no attribute '__me'
```

查看报错信息，告诉我们没有`__name`那个属性，果然隐藏了。在类的外面无法调用。

如果要调用那些私有化属性怎么办？可以使用property函数 。

****

```python
>>>class protectme(object):
    def  __init__(self):
        self.me='deng'
        self.__name='wen'
    @property
    def name(self):
        return self.__name
>>>p=protectme()
>>>print('p.name')
wen
```

从上面可以看出，用了@property函数之后，再调用那个方法的时候 ，用p.name的形式，就像在调用以往非私有化属性一样。

### 4.6 特殊属性和方法

在任何类中，都有一些特殊的属性和方法，它们的特殊性从表现就能看出来，通常用双下划线开头和结尾。之所以特殊，是因为它们跟你们自己写的或者其他不是以“__”开头和结尾的属性、方法有所差异。

#### 4.7.1`__dict__`

要访问类或者实例的属性必须通过“object.attribute”的方式，这是我们已经熟知的了。在这个认知的基础上，请思考：类或者实例属性在python中是怎样存储的？如何修改，增加、删除属性，以及我们能不能控制这些属性？

```python
>>>class A(object):
    pass
>>>a=A()
>>>dir(a)
['__class__', '__delattr__', '__dict__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__gt__', '__hash__', '__init__', '__init_subclass__', '__le__', '__lt__', '__module__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__setattr__', '__sizeof__', '__str__', '__subclasshook__', '__weakref__']
>>>dir(A)
['__class__', '__delattr__', '__dict__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__gt__', '__hash__', '__init__', '__init_subclass__', '__le__', '__lt__', '__module__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__setattr__', '__sizeof__', '__str__', '__subclasshook__', '__weakref__']
```

用dir()能够查看类的属性和方法，从上面的结果可以看出，数量不少，因为我们写的那个类里面只有pass，所以在列出的结果中，都是以“__”开头和结尾的，这些都是所谓的特殊属性和方法。

从众多的内容中寻觅出`__dict__`，之所以选它，是因为`__dict__`保存了某些机密。

```python
>>>class spring(object):
    season="the spring of class"
>>>spring.__dict__
mappingproxy({'__module__': '__main__', 'season': 'the spring of class', '__dict__': <attribute '__dict__' of 'spring' objects>, '__weakref__': <attribute '__weakref__' of 'spring' objects>, '__doc__': None})
```

从结果来看，有一个键'season'，它是这个类的属性，其值就是类属性的数据。

```python
>>>s=spring() #实例化
>>>s.__dict__
{}
```

实例属性的`__dict__`是空的。

```python
>>>s.season
'the spring of class'
```

s.season指向了spring.season。

```python
>>>s.season='the spring of instance'
>>>s.__dict__
{'season': 'the spring of instance'}
```

这样，实例属性里面就不为空了。这时候建立的实例属性和上面的那个s.season重名，并且把原来的“遮盖了”。

```python
>>>s.__dict__['season']#通过键值对方式查询
'the spring of instance'
>>>s.season
'the spring of instance'
```

我们再查看那个类属性如何？

```python
>>>spring.__dict['season']
'the spring of class'
>>>spring.__dict__
mappingproxy({'__module__': '__main__', 'season': 'the spring of class', '__dict__': <attribute '__dict__' of 'spring' objects>, '__weakref__': <attribute '__weakref__' of 'spring' objects>, '__doc__': None})
>>>spring.season
'the spring of class'
```

spring的属性没有受到实例属性的影响。

按照前面讲述的类属性和实例属性的操作，如果将实例属性（s.season）删除，会不会回到实例属性`s.__dict__`为空？

****

````python
>>>del s.season
>>>s.__dict__
{}
>>>s.season
'the spring of class'
````

果然打回原形。

当然，你可以定义其他名称的实例属性，它一样被存储到`__dict__`里面：

```python
>>>s.lang='python'
>>>s.__dict__
{'lang': 'python'}
```

这样做仅仅是改变了实例的`__dict__`内容，对`spring.__dict__`无任何影响。

```python
>>>spring.flower='peach'
mappingproxy({'__module__': '__main__', 'season': 'the spring of class', '__dict__': <attribute '__dict__' of 'spring' objects>, '__weakref__': <attribute '__weakref__' of 'spring' objects>, '__doc__': None, 'flower': 'peach'})
>>>spring.__dict__['flower']
'peach'
```

类的`__dict__`被更改了，类属性中增加了一个flower属性。但是实例的`__dict__`如何？

```python
>>>s.__dict__
{'lang': 'python'}
>>>s.flower
'peach'
```

通过上面的探讨，是不是基本理了实例和类的`__dict__`，并且也看到了属性的变化特点。特别是，这些属性都是可以动态变化的，即你可以随时修改和增删。



属性如此，方法呢？

```python
>>>class spring(object):
    def tree(self,x):
        self.x=x
        return self.x
>>>spring.__dict__
mappingproxy({'__module__': '__main__', 'tree': <function spring.tree at 0x00000195BF9D8598>, '__dict__': <attribute '__dict__' of 'spring' objects>, '__weakref__': <attribute '__weakref__' of 'spring' objects>, '__doc__': None}) 
```

结果跟前面讨论属性差不多，方法tree()也在`__dict__`里面。

```python
>>>t=spring()
>>>t.__dict__
{}
```

又跟前面一样，虽然建立了实例，但是实例的`__dict__`中没有方法。接下来执行：

```python
>>>t.tree('canglaoshi')
'canglaoshi'
```

果然如此，这样也印证了实例t和self的关系，即实例方法（t.tree('canglaoshi')）的第一个参数（self，但没有写出来）绑定实例t，透过self.x来设定值，给`t.__dict__`添加属性值。

换一个角度看看：

```python
>>>class spring(object):
    def tree(self,x):
        return x    
```

这个方法中没有将x赋值给self的属性，而是直接return，结果是：

``` python
>>>s=spring()
>>>s.tree('liushu')
'liushu'
>>>s.__dict__
{}
```

现在需要对python中的一个观点：“一切皆对象”在深入领悟。以上不管是类还是实例的属性和方法，都符合object.attribute格式，并且属性类似。

#### 4.7.2 `__slots__`

`__slots__`能够限制属性的定义，但是这不是它存在的终极目标，它存在的终极目标应该是在编程中非常重要的一个方面：优化内存使用。在某些编程中，优化内存是非常重要的。

```python
>>>class spring(object):
    __slots__=('tree','flower')
>>>dir(spring)
['__class__', '__delattr__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__gt__', '__hash__', '__init__', '__init_subclass__', '__le__', '__lt__', '__module__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__setattr__', '__sizeof__', '__slots__', '__str__', '__subclasshook__', 'flower', 'tree']
```

仔细看看dir()的结果，已经没有`__dict__`属性了。也就是说`__slots__`把`__dict__`挤出去了，返回来看看，没有`__slots__`，现在它进入类的属性。

```python
>>>spring.__slots__
('tree','flower')
```

从这里可以看出，类spring有且仅有两个属性，并且返回的是一个元组对象。

```python
>>>t=spring()
>>>t.__slots__
('tree','flower')
```

实例化之后，实例的`__slots__`与类的完全一样，这跟前面的`__dict__`大不一样了。

```python
>>>spring.tree='liushu'
```

通过类，先赋予一个属性值。然后检验一个实例能否修改这个属性：

```python
>>>t.tree='world'
Traceback (most recent call last):
  File "<pyshell#13>", line 1, in <module>
    t.tree='world'
AttributeError: 'spring' object attribute 'tree' is read-only
```

不能修改。因为前面已经通过类给这个属性赋值了，不能用实例属性来修改。只能通过类属性来修改。

但是对于没有用类属性赋值的，可以通过实例属性：

```python
>>>t.flower='world'
>>>t.flower
'world'
>>>spring.flower
<member 'flower' of 'spring' objects> 
```

属性实例的值并没有传回到类属性，你也可以理解为新建立了一个同名的实例属性。如果再给类属性赋值就会发生之前一样的情况。

```python
>>>spring.flower='suzhou'
>>>t.flower
'suzhou'
```

当然，此时再给t.flower重新赋值，就会报出跟前面一样的错误。

```python
>>>t.flower='world'
Traceback (most recent call last):
  File "<pyshell#19>", line 1, in <module>
    t.flower='world'
AttributeError: 'spring' object attribute 'flower' is read-only
```

看来`__slots__`已经把实例属性牢牢把控了起来，但本质上是为了优化内存。诚然，这种优化会在有大量的实例时显出效果。

#### 4.7.3 `__getattr__`、`__setattr__`和其他类似方法

结合4.7.2节内容，看一个例子。

****

```python
>>>class A(object):
    pass
>>>a=A()
Traceback (most recent call last):
  File "<pyshell#24>", line 1, in <module>
    a.x
AttributeError: 'A' object has no attribute 'x'
```

x不是实例的成员（“成员”笼统指类的属性和方法）。如果访问a.x，它不存在，那么就要转向某个操作。我们把这种情况称之为“拦截”。在python中，方法具有这种“拦截”能力。

- `__setattr__`(self,name,value)：如果要给name赋值，就调用这个方法。
- `__getattr__`(self,name)：如果name被访问，同时它不存在，此方法被调用。
- `__getattribute__`(self,name)：当name被访问时自动被调用（注意：这个仅能用于新式类），无论name是否存在，都要被调用。
- `__delattr__`(self,name)：如果要删除name，这个方法就被调用。

```python
>>>class A(object):
    def __getattr__(self,name):
        print('you are getattr')
    def __setattr__(self,name,value):
        print('you are setattr')
        self.__dict__[name]=value
```

类A是新式类，除了两个方法，没有别的属性。

```python
>>>a=A()
>>>a.x
you are getattr
```

依然调用了不存在的属性a.x，按照开头的例子是要报错了。但是，由于在这里使用了`__getattr__`(self,name)方法，当发现x不存在于对象的`__dict__`中，就调用了`__getattr__`拦截成员。

```python
>>>a.x=7
you are getattr
```

给对象的属性赋值时，调用了`__setattr__`(self,name,value)方法，这个方法中有一句`self.__dict__[name]=value`，通过这个语句，就将属性和数据保存到了对象的`__dict__`中，如果再调用这个属性：

```python
>>>a.x
7
```

x已经存在于对象的`__dict__`之中。

在上面的类中，当然可以使用`__getattribute__`(self,name)属性，因为它是新式类，并且，只要访问属性就会调用它。例如：

```python
>>>class B(object):
    def __getattribute__(self,name):
        print('you are using getattribute')
        return object.__getattribute__(self,name)
```

为了与前面的类区分，重新搞一个类，在类的方法`__getattribute__`()中使用return  object.`__getattribute__`(self,name)。

再来访问一个不存在的属性：

```python
>>>b=B()
>>>b.y
you are using getattribute
Traceback (most recent call last):
  File "C:/Users/storm/Desktop/1.py", line 6, in <module>
    b.y
  File "C:/Users/storm/Desktop/1.py", line 4, in __getattribute__
    return object.__getattribute__(self,name)
AttributeError: 'B' object has no attribute 'y'
```

访问不存在的成员，立刻被`__getattibute__`拦截了，虽然最后还是要报错的。

```python
>>>b.y=8
>>>b.y
you are using getattribute
8
```

当给其赋值后，意味着其已经在`__dict__`里面了，再调用，依然被拦截，但是由于其已经在`__dict__`内，所以会把结果返回。

特别注意，在这个方法中，没有使用`return self.__dict__[name]`，因为 如果用这样的方式就是访问`self.__dict__`，只要访问类的某个属性，就要调用`__getattribute__`，这样就会导致无限递归下去（死循环）。要避免之。

****

```python
>>>class Rectangle(object):
    ```the width and length of rectangle```
    def __init__(self):
        self.width=0
        self.length=0
    def setsize(self,size):
        self.width,self.length=size
    def getsize(self):
        return self.width,self.length
>>>r=rectangle()
>>>r.width=3
>>>r.length=4
>>>print(r.getsize())
>>>r.setsize((30,40))
>>>print(r.width)
>>>print(r.length)
```

```python
(3,4)
30
40
```

这段代码已经可以正确运行，但是，作为一个精益求精的程序员，总觉得那种调用方式还有可以改进的空间。比如，要给长宽赋值的时候，必须赋予一个元组，里面包含长和宽。这个能不能改进一下？

```python
>>>class Rectangle(object):
    ```the width and length of rectangle```
    def __init__(self):
        self.width=0
        self.length=0
    def setsize(self,size):
        self.width,self.length=size
    def getsize(self):
        return self.width,self.length
    size=property(getsize,setsize)
>>>r=rectangle()
>>>r.width=3
>>>r.length=4
>>>print(r.size())
>>>r.size((30,40))
>>>print(r.width)
>>>print(r.length)
```

以上代码中因为加了一句size=propertty(getsize,setsize)，使得调用方法更优雅了。原来用r.getsize()，现在使用r.size，就好像调用一个属性一样。

虽然优化了上面的代码，但是还没有和本节讲述的特殊的方法拉上关系，所以，还要继续改写。

****

```python
>>>class newrectangle(object):
    def __init__(self):
        self.width=0
        self.length=0
    def __setattr__(self,name,value):
        if name=="size":
            self.width,,self.length=value
        else:
            self.__dict__(name)=value
    def __getattr__(self,name):
        if name=="size":
            return self.width,self.length
        else:
            raise AttributeError
>>>r=newrectangle()
>>>r.width=3
>>>r.length=4
>>>print(r.size())
>>>r.size((30,40))
>>>print(r.width)
>>>print(r.length)
```

除了类的样式变化之外，调用方式没有变，结果是一样的。

#### 4.7.4 获得属性顺序

通过实例获取其属性，如果在`__dict__`中有，就直接返回其结果；如果没有，会到类属性中找。

```python
>>>class A(object):
    author='dengwen'
    def __getattr__(self,name):
        if name!='dengwen':
            return 'from starter to master'
>>>a=A()
>>>print(a.author)
>>>print(a.lang)        
```

运行结果：

```python
dengwen
from starter to master
```

当a=A()后，并没有为实例建立任何属性，或者说实例的__dict__是空的（意思是说没有某些属性值）。但是如果要查看a.author，因为实例的属性中没有，所以就去类属性中找，发现果然有，于是返回其值qiwsir。但是，找a.lang时候，不仅实例属性中没有，类属性中也没有，于是就调用了__getattr__()方法。幸好在这个类中有这个方法，如果没有__getattr__()方法呢？如果没有定义这个方法，就会引发AttributeError。
这就是通过实例查找特性的顺序。

### 4.8 迭代器

我们已经知道，对序列（列表、元组）、字典和文件都可以用iter()方法生成迭代对象，然后用next()方法访问。当然，这种访问不是自动的，如果用for循环，就可以自动完成上述访问了。

如果用dir（list）、dir（tuple）、dir（file）、dir（dict）来查看不同类型对象的属性，会发现它们都有一个名为__iter__的东西。这应该引起读者的关注，因为它和迭代器（iterator）、内置的函数iter()在名字上很像，除了前后的双下画线。望文生义，我们也能猜出它肯定是跟迭代有关的东西。当然，这种猜测也不是没有根据的，其重要根据就是英文单词，如果它们之间没有一点关系，肯定不会将命名设置的一样。

`__iter__`就是对象的一个特殊方法，它是迭代规则的基础。或者说，如果对象没有它，就不能返回迭代器，就没有next()方法，就不能迭代。

如果读者用的是Python 3.x，迭代器对象实现的是`__next__`()方法，不是next()。并且，在Python 3.x中有一个内建函数next()，可以实现next（it），访问迭代器，这相当于Python 2.x中的it.next()（it是迭代对象）。

#### 4.8.1 `__iter__()`

类型是list、tuple、file、dict的对象有`__iter__()`方法，标志着它们能够迭代。

```python
>>>class myrange(object):
    def __init__(self,n):
        self.i=0
        self.n=n
    def __iter__(self):
        return self
    def next(self):
        if self.i<self.n:
            i=self.i
            self.i+=1
            return i
        else:
            raise StopIteration()
>>>x=myrange(7)
>>>print('x.next()=>',x.next())
>>>print('x.next()=>',x.next())
>>>print('-----for loop-----')
>>>for i in x:
    print i
```

运行结果：

```python
x.next()=> 0
x.next()=> 1
2
3
4
5
6
```

以上代码的含义，使自己仿写了拥有range()的对象，这个对象是可迭代的，分析如下：

- `__iter__（）`是类中的核心，它返回了迭代器本身，实现了`__iter__()`方法的对象，即意味着其可迭代。
- 含有next()的对象就是迭代器，并且在这个方法中，在没有元素的时候要发起StopIteration()异常。

换一种调用方式：

****

```python
>>>x=myrange(7)
>>>print (list(s))
>>>print('x.next()=>',x.next())
```

运行结果：

```python
[0,1,2,3,4,5,6]
x.next()=>
Traceback (most recent call last):
File "21401.py", line 26, in <module>
print "x.next()==>", x.next()
File "21401.py", line 21, in next
raise StopIteration()
StopIteration
```

print list(x)将对象返回值都装进了列表中并打印出来，这个正常运行了。最终，指针移动到了迭代对象的最后一个，next()方法没有检测，也不知道是不是要停止了 ，它还要继续 下去，当继续下一个的时候，才发现没有元素了，于是返回了StopIteration()。

在使用列表的时候，需要将列表内容一次性都读入到内存中，这就增加了内存的负担。如果列表太大 ，就有内存溢出的危险了。这时候就需要迭代对象。比如斐波那契数列：

****

```python
>>>class  fibs(object):
    def __init__(self,max):
        self.max=max
        self.a=0
        self.b=1
    def __iter__(self):
        return self
    def next(self):
        fib=self.a
        if fib>self.max:
            raise StopIteration
    self.a,self.b=self.b,self.a+sele.b
>>>fibs=Fibs(5)
```

运行结果：

`[0,1,1,2,3,5]`

#### 4.8.2 range()和xrange()



