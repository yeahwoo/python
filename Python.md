### 第一章 python基础
- Python语言拥有者是Python Software Foundation(PSF) 
- PSF是非盈利组织，致力于保护Python语言开放、开源和发展
- Python语言创立者：Guido van Rossum
- 2002年，Python 2.x，2008年，Python 3.x
- python特点
	1. 语法简洁
	2. 与平台无关 
	3. 粘性扩展 
	4. 开源理念
	5. 通用灵活
	6. 强制可读
	7. 支持中文
	8. 模式多样
	9. 类库丰富
 - python优点
	 1. 优点一：优雅、简单、明确
	 2. 优点二：强大的标准库
	 3. 优点三：良好的可扩展性
- 缺点
	1. 缺点一：运行速度慢
	2. 缺点二：加密难
	3. 缺点三：缩进规则
	4. 缺点四：多线程灾难
- python的两种编程方式
	1. 交互式：对每个输入语句即时运行结果，适合语法练习
	2. 文件式：批量执行一组语句并运行结果，编程的主要方式
- 程序格式和语法
	- 缩进
		1. 严格明确：缩进是语法的一部分，缩进不正确程序运行错误
		2. 所属关系：表达代码间包含和层次关系的唯一手段 
		3. 长度一致：程序内一致即可，一般用4个空格或1个TAB
	- 注释
		1. 单行注释：以#开头，其后内容为注释
		2. 多行注释：以'''开头和结尾
	- 赋值理解
当我们写：a='ABC' 时，Python解释器干了两件事情：
（1）在内存中创建了一个'ABC'的字符串；
（2）在内存中创建了一个名为a的变量，并把它指向'ABC'。 也可以把一个变量a赋值给另一个变量b，这个操作实际上是把 变量b指向变量a所指向的数据，例如下面的代码：
		```python
		a='ABC'
		b=a 
		a='XYZ'
		print(b)
		```
		输出的结果是：`ABC`
	- 保留字
	![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/RTzRqL6ZB6oApxdE.png)
- 数据类型
	- 整型
	在整数除法中，除法（/）计算结果是浮点数，即使是两个 整数恰好整除，结果也是浮点数，如果只想得到整数的结 果，丢弃可能的分数部分，可以使用地板除（//），整数的 地板除（//）永远是整数，即使除不尽。
	地板除（//）只取结果的整数部分，Python还提供一个余数 运算（%），可以得到两个整数相除的余数。
	- 复数
	复数由实数部分和虚数部 分构成，可以用a + bj,或者complex(a,b)表示， 复数的实部a和虚部b都是浮点型。
	- 常量
	在Python中，通常用全部大写的 变量名表示常量。
	Python中有两个比较常见的常量，分别为：PI和E。
	- 字符串
	![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/M64VjCjxyiVPnHwR.png)
	使用：
		1. 索引：返回字符串中单个字符 <字符串>[M] "请输入带有符号的温度值: "[0] 或者 TempStr[-1]
		2. 切片：返回字符串中一段字符子串 <字符串>[M: N] "请输入带有符号的温度值: "[1:3] 或者 TempStr[0:-1]
- 函数
	eval：
	去掉参数最外侧引号并执行余下语句的函数。
		```python
		>>>eval("1")
		1
		>>>eval('"1+2"') 
		'1+2' 
		>>> eval('print("Hello")') 
		Hello 
		>>> eval("1+2") 
		3
### 第二章 基本图形绘制
- 库引用
	- 使用from和import保留字共同完成 
	```python
	from <库名> import <函数名> 
	from <库名> import * <函数名>(<函数参数>)
	```
	- 使用import和as保留字共同完成
	```python
	import <库名> as <库别名> 
	```
- 画笔函数
	- `turtle.penup()` 抬笔
	- `turtle.pendown()`落笔 
	- `turtle.pensize(width)`画笔宽度
	- `turtle.pencolor(color)`画笔颜色，color可以输字符串或三位RGB或RGB元组值
	- `turtle.forward(d)`向前画直线，d为距离（可负）
	- `turtle.circle(r, extent=None)`根据半径r绘制extent角度的弧形，extent默认360°
	- `turtle.setheading(angle)别名turtle.seth(angle)`改变画笔朝向（顺时针）
	- `turtle.left(angle`左转
	- `turtle.right(angle)`右转
- 循环
	- `range(N)` 产生 0 到 N-1的整数序列，共N个 
	- `range(M,N)` 产生 M 到 N-1的整数序列，共N-M个
	- `range(M,N.K)`K为步长
- 实例
![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/eOdi0zibLSYho1Qg.png )


### 第三章 基本数据类型
- 整数4种进制表示形式：
	- 十进制：1010, 99, -217 
	- 二进制，以0b或0B开头：0b010, -0B101 
	- 八进制，以0o或0O开头：0o123, -0O456 
	- 十六进制，以0x或0X开头：0x9a, -0X89
- 浮点数：
	- 浮点数取值范围和小数精度都存在限制，但常规计算可忽略 
	- 取值范围数量级约-10308至10308，精度数量级10-16
	- 浮点数间运算存在不确定尾数
		```python
		>>> 0.1 + 0.3
		0.4 
		>>> 0.1 + 0.2 
		0.30000000000000004(不确定尾数)
		```
		```python
		>>> 0.1 + 0.2 == 0.3 
		False 
		>>> round(0.1+0.2, 1) == 0.3 
		True
		```
	- `round(x, d)`对x四舍五入，d是小数截取位数
- 复数
	```python
	z = 1.23e-4+5.6e+89j 
	z.real 获得实部 
	z.imag 获得虚部
	```
- 数值运算
	- 数字类型的关系
		- 类型间可进行混合运算，生成结果为"最宽"类型 
		- 三种类型存在一种逐渐"扩展"或"变宽"的关系： 整数 -> 浮点数 -> 复数
		> 例如：123 + 4.0 = 127.0 (整数+浮点数 = 浮点数)
	
	- 数值运算函数
		- `round(x[, d])`:四舍五入，d是保留小数位数，默认值为0 
		 `round(-10.123, 2) 结果为 -10.12`
		 -	`divmod(x,y)`:商余，(x//y, x%y)，同时输出商和余数
		 `divmod(10, 3) 结果为 (3, 1)`
		 -	`pow(x, y[, z])`:幂余，(x**y)%z，[..]表示参数z可省略
		 `pow(3, pow(3, 99), 10000) 结果为 4587`
		- `complex(x)`:将x变成复数，增加虚数部分
		`complex(4) 结果为 4 + 0j`
- Math库
	![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/KwIWV3iFRAlWAMKg.png)
	![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/AoqCeBJcJRxfjyi2.png)
	![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/Vi7kXqWLAYiqnbeT.png)
	![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/rRiYPyOWwpAlFGYR.png)
- 字符串
	- 切片高级用法
	![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/oktmlfxbanaJs1t4.png)
	- 字符串操作符
		- `x + y`:连接两个字符串x和y
		- `n * x 或 x * n`:复制n次字符串x
		- `x in s`:如果x是s的子串，返回True，否则返回False
	- 字符串处理函数
		 ![输入图片说明](/imgs/2023-03-11/BiUVbFfZrfYBp9C0.png)
		![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/XFUgMl5bWOd8bbYI.png)
		![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/wRI1Nj4X8vAhpqWi.png)
		![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/H6H2npaXV8bxoysF.png)
		![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/W1P1mEggtxwCAsNe.png)
![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/TVb0wD7yjovJkpAS.png)
- 字符串格式化
![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/XFiCvnvYy4duumiz.png)
![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/8hRSUnIcTlvioHT4.png)
![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/rsHlttpyiOxzUrpS.png)
	```python
	>>>"{0:=^20}".format("PYTHON")
	'=======PYTHON======='
	>>>"{0:*>20}".format("BIT") 
	'*****************BIT'
	>>>"{0:b},{0:c},{0:d},{0:o},{0:x},{0:X}".format(425) 		
	'110101001,Ʃ,425,651,1a9,1A9'
	>>>"{0:,.2f}".format(12345.6789) 
	'12,345.68'
	>>>"{0:e},{0:E},{0:f},{0:%}".format(3.14) 	
	'3.140000e+00,3.140000E+00,3.140000,314.000000%'
	``` 
- 时间库
	![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/U9bLCQXfhDzsXQTu.png)
![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/yxsTmDWMXOG5cXjT.png)
![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/JJ5QwT6MCCVQwXGP.png)
![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/NohGG4bxQNdtj2mQ.png)
![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/rYrOhdRJlNHSEKiz.png)
![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/lQYFAYhu5qvKa8hp.png)
![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/82yxnRVPGL2fGMJj.png)![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/4vIWjxRNtXw9QMUr.png)
	![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/UeXACc46n06ihQRR.png)
### 第四章 控制结构
- 条件组合
	- `x and y`:与
	- `x or y`:或
	- `not x`:非
- 异常处理
	- ```python
	try:
		<语句块>
	except [异常类型]:
		<异常处理>
	```
	- 高级
	![输入图片说明](/imgs/2023-03-11/g1OhCuJeOhIkuExs.png)
- 循环
	- 字符串
	```python
	>>> for c in "Python123": print(c, end=",") 
	P,y,t,h,o,n,1,2,3,
	```
	- 文件
	fi是一个文件标识符，遍历其每行，产生循环
![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/L2NPyaSNrWFB4nHd.png)- random库
	- 用前导入`import random`
	- 基本随机函数
	![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/13M9Hxem9xqM0daD.png)
	- 扩展
	![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/2fZDFTYz6KYFQoyN.png)
	![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/EsEFsLOftNbNBHSR.png)
![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/SYKKujQmgZ2BFnli.png)
### 第五章 函数与代码复用
- 函数
	- 函数可以没有参数，但必须保留括号
	- 可选参数
	![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/dlpdxw04xTzIiVBN.png)
	- 可变参数：可不确定参数的总数量
![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/nw3f0Tm3cWUC4tV7.png)
- 参数传递
![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/1rtnp5e6EC10iAwG.png)
- 返回值
可以有返回值也可以没有，也可以有多个，可以有return也可没有，return后也可以跟多个返回值，逗号隔开，位置必须一一对应。
- 局部变量和全局变量
	- 局部变量和全局变量是不同变量
	- 局部变量是函数内部的占位符，与全局变量可能重名但不同
	- 函数运算结束后，局部变量被释放 
	- 可以使用global保留字在函数内部使用全局变量
	![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/VEAW2jOghnS3lfKT.png)
	- 局部变量为组合数据类型且未创建，等同于全局变量：在函数外面已经创建过的在函数内再创建就是局部变量
- lambda函数
```python
>>> f = lambda x, y : x + y 
>>> f(10, 15) 25 
>>> f = lambda : "lambda函数" 
>>> print(f())
```
- 递归
![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/GfxKqMLgKXe7ElDw.png)
- PyInstaller
	- 使用：`(cmd命令行) pyinstaller -F <文件名.py>`
	- 参数
	![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/UfKYuGNw37enT3HC.png)
	- 实例
	![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/yLDBKGUqTXKvliuD.png)
### 第六章 组合数据类型
- 集合
	- 集合是多个元素的无序组合
	- 集合用大括号 {} 表示，元素间用逗号分隔 
	- 建立集合类型用 {} 或 set() 
	- 建立空集合类型，必须使用set()
	```python
	>>> A = {"python", 123, ("python",123)} #使用{}建立集合 
	{123, 'python', ('python', 123)} 
	>>> B = set("pypy123") #使用set()建立集合 
	{'1', 'p', '2', '3', 'y'} 
	>>> C = {"python", 123, "python",123} 
	{'python', 123}
	```
	- 操作符
	![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/uGYun1aUBwGhtxTy.png)
	- 方法	![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/97VKzdwkQFuIUu63.png)
![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/CT5QTrdqtaospV2x.png)
- 元组
	- 元组是一种序列类型，一旦创建就不能被修改，因此没有特殊操作
	- 使用小括号 () 或 tuple() 创建，元素间用逗号 , 分隔 
	- 可以使用或不使用小括号
	- 定义
	```python
	>>> creature = "cat", "dog", "tiger", "human" 
	>>> creature 
	('cat', 'dog', 'tiger', 'human') 
	>>> color = (0x001100, "blue", creature) 
	>>> color 
	(4352, 'blue', ('cat', 'dog', 'tiger', 'human'))
	```
- 列表
	- 列表是一种序列类型，创建后可以随意被修改 
	- 使用方括号 [] 或list() 创建，元素间用逗号 , 分隔 
	- 列表中各元素类型可以不同，无长度限制
	- 操作
![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/F7cdgIYDwzUNlTyG.png)
![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/kxJZs9dZihOWFRCa.png)
- 字典
	- 字典类型是“映射”的体现
	- 键值对：键是数据索引的扩展 
	- 字典是键值对的集合，键值对之间无序 
	- 采用大括号{}和dict()创建，键值对用冒号: 表示
	- 定义和使用
	```python
	>>> d = {"中国":"北京", "美国":"华盛顿", "法国":"巴黎"} 
	>>> d 
	{'中国': '北京', '美国': '华盛顿', '法国': '巴黎'} 
	>>> d["中国"]
	'北京' 
	>>> de = {} ; 
	type(de) 
	<class 'dict'>
	```
	- 操作
	![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/vaaB7nrIwHOH28m1.png)
	![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/UjMKFlDO6ND3Be2H.png)
- jieba
![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/ZheI1ej9gHt9KVeH.png)
![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/MsO3OEEFR0dExHqy.png)
### 第七章 文件
- 文件的理解
	- 文件是数据的抽象和集合
	- 文件是存储在辅助存储器上的数据序列 
	- 文件是数据存储的一种形式 
	- 文件展现形态：文本文件和二进制文件
	- 文件文件和二进制文件只是文件的展示方式 
	- 本质上，所有文件都是二进制形式存储 
	- 形式上，所有文件采用两种方式展示
	- 由单一特定编码组成的文件，如UTF-8编码 
	- 由于存在编码，也被看成是存储着的长字符串 
	- 适用于例如：.txt文件、.py文件等
	- 直接由比特0和1组成，没有统一字符编码 
	- 一般存在二进制0和1的组织结构，即文件格式 
	- 适用于例如：.png文件、.avi文件等
- 文件的打开和关闭
	- 打开
	![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/DOxAPGdaTwOd1RIH.png)
	- 打开模式
	![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/D9zd3cxaf2hGwaFD.png)
	- 实例
	![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/2jcfpqS9JZHgRutj.png)
- 关闭
`<变量名>.close()`
- 读取![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/Llm6f1NBban9fomI.png)
![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/lcvLzjASPUgrre4W.png)
- 写入
![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/cxYXu7IhD3F0p6fG.png)
![输入图片说明](https://raw.githubusercontent.com/yeahwoo/python/master/imgs/2023-03-11/CBMgi3EzifVSmbcw.png)

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIxNDY1NzAxODUsLTExNzU2ODY0MjcsLT
I5NTcwNDk5MiwtMTc2ODg0MTE1OCwtMjAzMzQ1OTg1MCw0NTYx
MTA5OTVdfQ==
-->