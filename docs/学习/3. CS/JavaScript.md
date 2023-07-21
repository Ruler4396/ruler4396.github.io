
## 基本语法

- 按行执行

### 常量与变量
var 全局变量 少用
let 变量 可以先声明再赋值
const 常量 不可更改 声明的时候就要赋值

- 区分大小写
- 只声明不赋值 则值为`undefined`
- 要先声明再使用
- 变量可以随时更改 #数据类型 
- 重复声明无效，但是声明且赋值则会覆盖

- 变量提升
	- 自动将声明(而不包括赋值)提前到头部，然后一行行执行代码

```
console.log(a);
var a = 1;

//等价于下列代码

var a;
console.log(a);
a = 1;
//最终会输出undefined
```


- 注释
```
// 这是单行注释
/*这是
多行
注释
*/
```

- #区块 
	- 对于var命令 区块不构成单独的 #作用域
```
{
	var a = 1;
}

a // 1
```

### if语句
```
if (布尔值){
	语句;
}


//单行语句时可以用

if (布尔值) 语句;
```

赋值表达式 `=`
严格相等运算符 `===`
相等运算符 `==`

- 可以把常量写在等式左边

### if…else

### break

### ??label
```
LabelName:
	语句
```
相当于定位符，跳转到程序的任意位置

可以和break连用
```
{
	{
		语句;
		break LabelName;
	}
}

LabelName:
{
	语句;
}
```



## 杂项

! + Tab HTML容器
h1 +Tab

关注点分离
调用index.js文件
```
<script src="index.js">
</script>
```

Ctrl + <font color="#FFFFFF">`</font> 在VScode调出控制终端



## 数据类型
```
const i
username "John"; //String
const age 30; //number
const rate 4.5; //number
const isCool true; //boolean
function f() {} //function
const x null; //object 其实是null
[] //object
{} //object
const y undefined; //undefined
let z; //undefined

console.log(typeof 变量名) //输出数据类型
```
number 整数和小数
- 均为64位浮点数\*某些运算会转化为32位
	大于$2^{1024}$ 正向溢出 返回Infinity
	小于$2^{-1075}$ 负向溢出 返回0
	Number对象有MAX_VALUE和MIN_VALUE属性，返回可以表示的最大值和最小值
- 数值表示法
	采用科学计数法 e和E后跟整数表示整数部分
	小数点前的数字多于21位
	小数点后的0多于5个
- 进制
	0O或0o前缀的数值 八进制
	0x或者0X前缀的数值 十六进制
	0b或者0B的数值 二进制
	或者有前导0、且只用到0-7的八个阿拉伯数字的数值。
- +0和-0
	作为分母时，+0返回+Infinity，-0返回-Infinity
- NaN非数字
	不等于它本身
	0/0
	参与任何运算都为NaN
- 全局方法
	- #parseInt

String 文本
Boolean 布尔值 真/假
	以下为false
		undefined
		null
		false
		0
		NaN
		‘’(空字符串)
	一些特殊的也为ture
		[]
		{}
		
//原始类型
null 空
undefined 未定义
	声明变量但没有赋值
	调用函数没有实参
	对象没有赋值的属性
	函数没有返回值


字符串
//特殊值 基本没区别
object 各种值的集合
	array 数组
	function 函数

获取数据的类型 #typeof 

## 运算符
- #typeof 
- 前置逻辑运算符
	- !
- 相等运算符
	- ===
	- !==
	- ==
	- !=
- 比较运算符
	- >=
	- >
	- <
	- <=

## 模版字符串
```
const age = 30;

const username = "John";

console.log("My name is" + username + " and I am age " + age); 
//字符使用""包裹，变量两边用+

console.log(`My name is ${username} and I am age ${age}`); 
//前后使用``包裹，中间使用${变量名}
```

## 字符串内置方法
```
console.log(字符型变量名.length); //字符串长度

console.log(字符型变量名.toUpperCase()); //将全部字符大写 记得加上括号

console.log(字符型变量名.toLowerCase()); //将全部字符小写 记得加上括号

console.log(字符型变量名.substring(a,b)); //将字符串分割开，a和b是起始点和终止点 注意是从0开始

console.log(字符型变量名.substring(a,b).toUpperCase()); //substring返回字符串，可以接上别的方法

console.log(字符型变量名.split("")); //将字符串转化为数组，需要在""内提供分割单元 为空则按字符分割，可以为", "此时按提供的分割单元分割字符串
```

## 数组
```
const 变量名 = new 数组名(数据列表); //新建一个数组，用const定义的数组可以改变部分元素，改变或者全部或者时会报错

const 数组名[]; //用,分隔开数据，可以存入不同数据类型，字符型记得加上""

consloe.log(数组名); 

consloe.log(数组名[a]); //用索引来选择数组

数组名[a] = 数据; //可以用赋值的方法给数组新的值

数组名.push(数据); //在末尾新增元素

数组名.unshift(数据); //在头部新增元素

数组名.pop(); //删除末尾元素

Array.isArray(数组名); //判断是否为数组，返回布尔值

数组名.indexOf(数组元素); //返回数组引索

```

## 对象
```
const 对象名1 = {

	属性1: 数据,
	属性2: 数据,
	数组名: [数据列表], //用:和，定义数据
	
	对象名2: {
		属性A: ,
		属性B: ,
	},
	
};

const {
	属性1,
	属性2,
	数组名:{数据}
} = 对象名; //将属性从类中提取出来，可以不通过对象而直接调用
console.log(属性2);

对象名.属性名 = 数据; //在对象中新建一个属性
```

## 对象数组和json
```
const 数组名 = [ //用[]定义数组，{}表示数组里的对象，数据后用,
	{
		属性1: 数据,
		属性2: 数据 //注意最后一个不需要,
	}，
	
	{
		属性A: 数据,
		属性B: 数据
	},
];

console.log(数组名[1].text); //用数组名和引索调用对象，.的意思是下一级目录?

const 变量名 = JSON.stringift(对象数组名); //将对象数组转化为JSON格式

```

```
{
	{
		"属性1": 数据,
		"属性2": 数据 //属性名会被打上双引号，对象数组名等信息不会保留，只保留对象的属性
	},
	
	{
		"属性A": 数据,
		"属性B": 数据
	},
}
```

- 三等号 不考虑数据类型

```
变量名 of 对象数组名 //在对象数组中声明一个循环变量

变量名.属性名 //此时循环变量变量就是对象数组中的每一个对象，用.可以访问每个对象中的相同属性

//和循环语句搭配使用
```

## 函数
- 全局方法
	- 将字符串转化为整数
```
parseInt('123') //123

parseInt('   223') //223
// 自动删除空格

parseInt(1.3)// parseInt('1.3')
//参数不是字符串的时候，将会转为字符串再运算
```


如果字符串的第一个字符不能转化为数字（后面跟着数字的正负号除外），返回`NaN`。

```
parseInt('abc') // NaN
parseInt('.3') // NaN
parseInt('') // NaN
parseInt('+') // NaN
parseInt('+1') // 1
```

所以，`parseInt`的返回值只有两种可能，要么是一个十进制整数，要么是`NaN`。

如果字符串以`0x`或`0X`开头，`parseInt`会将其按照十六进制数解析。

```
parseInt('0x10') // 16
```

如果字符串以`0`开头，将其按照10进制解析。

```
parseInt('011') // 11
```

对于那些会自动转为科学计数法的数字，`parseInt`会将科学计数法的表示方法视为字符串，因此导致一些奇怪的结果。

```
parseInt(1000000000000000000000.5) // 1
// 等同于
parseInt('1e+21') // 1

parseInt(0.0000008) // 8
// 等同于
parseInt('8e-7') // 8
```
```