# python 数据分析之前奏

## 1.课程内容导学

1. 掌握表示、清洗、统计和展示数据的能力

2. 如何理解一组数据表达的含义

3. 摘要：有损地提取数据特征的课程 

## 2.python 语言开发工具

|   本工具类   |    集成工具类    |
| :----------: | :--------------: |
|     IDLE     |     pycharm      |
| Sublime Text | Anaconda &Spyder |

**适合自己的才是最好的**

## 3.Anaconda的基本使用

1. 集成了各种开发工具
2. 来源于conda 
3. 包管理与pip类似
4. 环境空间—root 展示了各种包

### 3.1spyder

* 左侧编辑区 （可以增加风格）
* 右上 文件帮助和导航
* Ipython 环境(交互式的编程环境)
  1. ？的使用（函数或变量的前后加？）
  2. %run
  3. %magic(%hist & %pdb & %reset & %who & %time(it)  statement(表示代码))

```python
a=np.random(1000,1000)
%timeit np.dot(a,a)
%who
%hist
```

***

# 数据分析之表示

## 1.numpy 入门

### 1.1数据的维度

* 一个数据到一组数据

* 维度-数据的组织形式

  1. 一维数据  一维数据由对等关系的有序或无序的数据构成，采用线性方式组织

  2. 对应列表、数组和集合等概念

     * 列表：数据类型可以不同
     * 数组：数据类型相同

  3. 二维数据 由多个一维数据构成，是一维数据的组合形式-列表。

     * 表格是典型的二维数据，表头是二维数据的一部分
     
  4. 多维数据由一维数据或二维数据在新维度上形成
  
  5. 高维数据 仅利用最基本的二元关系（键值对）展示数据间的复杂结构
## 1.2 numpy

* numpy是一个开源的Python科学计算基础库
* 一个强大的N维数据对象ndarray
* 广播功能函数
* 整合C++/Fortran代码的工具
* 线性函数、傅里叶变换、随机数生成等功能
* numpy 是Scipy、Pandas等数据处理或科学计算的基础

### 1.3Numpy 的引用

```python
import numpy as np
```

* 为什么需要数组类型

例子:计算a^2+b^3

```python
def pySum(): 
	a=[0,1,2,3,4]
	b=[9,8,7,6,5]
	c=[]
	for i in range(len()):
		c.append(a[i]**2+b[i]**3)
	return c 
print(pySum)
```

```python
import numpy as np
def npsum():
	a=np.array([0,1,2,3,4])
	b=np.array([9,8,7,6,5])
	c=a**2+b**3
	return c
print(npsum())
```



​     

  





