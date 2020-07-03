# kotlin基本类型 #
## 数字类型 ##

-  整型

     类型		长度（位数）   大小（字节数）
	
     Byte 		8			1	

     Short		16			2

     Int		32			4

     Long		64			8


未超过Int长度的值默认为Int，超过则为Long（也可以显示指定类型1000L）


- 浮点数
	类型			长度			大小

	Float		32			4

	Double		64			8
	

申明的浮点数默认为Double类型（可以显示指定为Float类型3.14F）


**不可隐式转换**如不能

	 val a:byte = 1
	 val b:Int = a  // 错误
	 var c:Int = a.toInt() /正确
**运算符能重载，对类型进行转换**

    var i7 = 2
	var i8 = 3L
	println((i7+i8).javaClass)  //输出Long

整数除法，结果为整数（丢弃小数部分）。如需返回小数可将其中一个数转化为浮点数


- 位运算（只用于Int和Long）


## 字符 ##
Char:用 '' 括起来  var a = '1'

## 布尔Boolean ## 
布尔类型有两个值  true和false，其运算有 与（&&）或（||）非（！）

## 数组 ##

	`var arr13:Array<Int?> = Array(5){i -> i*1 }` 
原生类型数组
ByteArray、 ShortArray、IntArray 等等

## 字符串 ##
字符串用 String 类型表示。字符串是不可变的。 字符串的元素——字符可以使用索引运算符访问: s[i]。

    var str = "abc"
	println(str)
	println("str.length is ${str.length}")






    