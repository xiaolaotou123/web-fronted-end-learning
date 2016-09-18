#### javascript基础


##### 老版浏览器不支持JavaScrip

* 使用`<!--与//-->`标记
* 使用`<noscript>...</noscript>`标签

##### JS变量

* 变量关键字var
	变量无var关键字为全局变量
* 变量作用域
	1. 局部变量 函数级作用域
	2. ES6支持块级作用域,let关键字

##### JS不常用操作符

* delete:用来删除对象,对象的属性或者数组中的元素
* with:简化对象的使用,执行效率很低

	```javascript
	with (objectName) {
		//objectName对象的语句块
	}
	```

##### JS基本数据类型

* 获取基本数据类型的字符串值
	```
	var baseType = typeof(foo);
	```

* 基本数据类型
	```
	undefined(等同于void 0)
	boolean
	number(NaN,NaN不全等于任何数包括NaN;Infinity;一些浏览器不支持八进制)
	object(null,null为特殊的object对象,只有一个值null)
	string
	symbol(ES6新增)
	function
	```

* 基本数据类型转换
	转boolean类型

	| type      | result   |
	|-----------|----------|
	| 0/NaN     | false    |
	| 其他number | true     |
	| ''        | false    |
	| 其他string | true     |
	| null      | false    |
	| 其他object | true     |
	| undefined | false    |
	| function  | true     |

	转string类型

	| type      | result                   |
	|-----------|----------------------------|
	| number    | 数字字符串/'NaN'             |
	| boolean   | 'true'/'false'             |
	| null      | 'null'                     |
	| 其他object | 调用toString()或'undefined' |
	| undefined | 'undefined'                |

	转number类型

	| type       | result   |
	|------------|----------|
	| 数字字符串             | 数字值               |
	| 非数字字符串         | NaN      |
	| true       | 1        |
	| false      | 0        |
	| null       | 0        |
	| 其他object  | 调用toString()或NaN |
	| undefined  | NaN      |

	转object类型
	
	| type      | result             |
	|-----------|--------------------|
	| number    | new Number(value)  |
	| string    | new String(value)  |
	| boolean   | new Boolean(value) |
	| null      | 抛出异常                                         |
	| undefined | 抛出异常                                         |

##### 函数对象(Function产生的)

函数就是构造器对象

* 创建函数

	```javascript
	// 方式1
	function fo(){
		return 'fo';
	}

	// 方式2
	var foos = fooo(){
		return 'fooo';
	}

	// 方式3,构造函数
	var foo = new Function(
	'x', 'y', 'z', //arguments
	'return x + y + z;' //method body
	);
	```

* 属性和方法

	```
	arguments                    函数参数"数组"对象,不是Array对象;不能显示地创建,只有函数开始时才能使用
	arguments.callee             当前函数的引用,用于递归
	arguments.callee.length      形参长度
	arguments.length             实参长度
	length                       定义函数时期望的参数个数
	caller                       返回1个对函数的引用,该函数调用当前函数;
	对于函数来说,此属性只有在函数执行时才定义.
	若函数是由顶层调用的,则caller包含的就是null;
	若在字符串上下文中使用此属性,则结果和toString()一样,显示的是函数的反编译文本
	prototype                    函数对象的原型属性,必要的
	constructor                  构造方法
	toString()                   获取函数定义的代码
	valueOf()                    获取函数定义的代码
	Function.prototype函数对象是个例外,无prototype属性
	```

##### JS对象
所有对象继承自最顶层对象为Object

* 对象公共属性

	```
	length                        长度
	prototype                     原型(函数对象拥有)
	constructor                   构造方法
	__proto__                     每个对象都有此隐藏属性,指向它所对应的原型对象(原型链基于此属性)
	toString()                    对象(实例)值的字符串
	valueOf()                     对象(实例)的值
	toLocalString()               对象(实例)本地化的值
	isPrototypeOf(obj)            判断1对象是否存在于另1对象的原型链中
	```

* 创建对象

	```javascript
	// 使用object()构造函数
	var foo = new Object();
	foo.name = 'foo';
	foo["date"] = '2016-09-11'; // 联合数组中数组元素通过其字符串名称进行访问
	foo.doAction = function() {
		alert('foo');
	}
	var addAttr = function(attr) {
		foo.attr = attr;
	}
	foo.addAttr = addAttr;
	foo["isEmpty"] = function() {
		if(foo.trs) {
			return true;
		}
		return false;
	}

	// 对象直接量
	var obj = {};
	obj.name = 'foo';
	var o = {
		name : 'foo';
		doAction : function() {
			alert('foo');
		}
	};

	// 构造函数
	function foo() {
		this.name = 'foo';
		this.doAction = function() {
			alert('foo');
		}
	}
	var f = new foo(); // 创建对象实例
	f.doAction();

	function foos() {
		foos.name = 'foos';
		foos.doAction = function() {
			alert('foos');
		}
	}
	var fo = new foos(); // 创建对象实例
	// fo.doAction(); 错误地调用方法
	foos.doAction(); // 正确地调用方法
	var fooo = foos(); //引用函数对象
	fooo.doAction();
	/**
	* 函数名指向函数对象本身,表示调用函数时产生函数对象实例,该对象实例的名称就是函数名
	* 而this关键字指向被定义的对象,代表由new关键字创建的该对象的所有实例;
	* 严格模式下,this被设置为undefined;非严格模式下,this被设置指向全局对象
	* 回调函数的this由回调函数调用者决定的
	*/
	```

* 属性和方法

	```javascript
	// 实例属性和方法
	Date date = new Date(2016, 9, 13);
	date.lunar = '08-13';
	delete date.lunar; // 删除实例属性
	// 静态属性和方法
	var pi = Math.PI;
	delete Math.PI; // 删除静态属性
	// 原型属性与方法
	String.prototype.PI = Math.PI+'';
	delete String.prototype.PI; // 删除原型属性
	```

* 原型继承

	```javascript
	function foo() {
		this.name = 'foo';
		this.doAction = function() {
			window.document.write('foo');
		}
	}
	function subFoo() {
		this.lable = 'subFoo';
	}
	// subFoo.prototype = foo().prototype;
	subFoo.prototype = new foo(); //继承foo对象
	// Test
	var subFooIns = new subFoo();
	alert(subFooIns.name);
	subFooIns.doAction();
	```

* Namespace

	```javascript
	function namespace(namespaceString) {
		var temp = []; // Declare a empty array
		var array = namespaceString.split('.');
		for (var i=0; i<array.length; i++) {
			temp.push(array[i]);
			// Add new objects to window object
			// eval('window.' + temp.join('.') + '=function(){}');
			eval('window.' + temp.join('.') + '={}');
		}
	}
	
	var _namespace = namespace('com.maximum.demo');
	```

##### JS全局对象

* 属性

	```
	Infinity                      正无穷大
	java                          java.*包层级的一个JavaPackage
	NaN                           非数字
	Packages                      根JavaPackage对象
	undefined                     未定义的值
	```

* 方法

	```
	decodeURI(URIstring)          解码某个编码的URI
	decodeURIComponent(URIstring) 解码一个编码的URI组件
	encodeURI(URIstring) 	      把字符串编码为URI,'/?:@&=+$,#'是不会进行转义的
	encodeURIComponent(URIstring) 把字符串编码为URI组件,'/?:@&=+$,#'会进行转义的
	escape(string)                对字符串进行编码,空格,标点,重音符号及其他非 ASCII字符都用%xx编码代替
	eval(string) 	              把js字符串作为脚本代码来执行
	getClass(javaobj)             获取JavaObject的JavaClass
	isFinite(number)              某个值是否为无穷大
	isNaN(x)                      某个值是否为数字
	Number(object)                把对象的值转换为数字
	parseFloat(string)            字符串转换为浮点数
	parseInt(string, radix)       字符串转换为整数,radix默认为10(jinzhi1),radix范围2~36
	String(object)                把对象的值转换为字符串
	unescape(string)              对由escape()编码的字符串进行解码
	```

##### JS内置对象

* String对象

	创建对象
	```javascript
	var str = new String('foo'); // 方式1
	var str2 = 'foo'; // 方式2
	```
	属性和方法
	```
	charAt(index)                 获取指定位置字符,index范围0~length-1
	charCodeAt(index)             获取指定位置字符的Unicode码,超出0~65535,返回NaN
	concat(str)                   连接字符串
	fromCharCode(UnicodeCode)     从字符编码创建一个字符串
	indexOf(str)                  查找str位置,找不到,返回-1
	lastIndexOf(str)              倒序查找str位置,找不到,返回-1
	match(str|regex)              匹配字符串或正则,若找不到,返回null;
	若找到并未指定全局选项g,返回1个数组,数组第1个元素存放第1个完整匹配的字符串,其余元素存放与正则表达式的子表达式匹配的文本,
	数组index属性是匹配字符串在原字符串中位置,input属性是对原字符串的引用;
	若找到并指定全局选项g,返回1个存放所有完全匹配字符串的数组
	search(regex)                 查找与正则匹配的值,返回第1个匹配字符串索引,若找不到返回-1
	replace(str1|regex, str2)     替换str1为str2;若regex指定全局g,则替换所有匹配的字符串;
	str2可以是1个(匿名)函数,以匹配的字符串作为参数调用此函数,返回结果替换字符串
	slice(start, end)             提取字符串某个部分
	substr(start, length)         抽取从start下标开始length长度的字符串
	substring(start, end)         抽取从start下标开始end-1处结束的字符串
	toUpperCase(str)              转换为大写
	toLowerCase(str)              转换为小写
	split(str)                    根据str分割为数组
	valueOf()                     获取某个字符串原始值
	toString()                    获取字符串值
	```
	字符串在网页中处理外观的方法
	```
	big()方法：加大显示字符,返回字符串
	blink()方法：使字符串闪烁,返回字符串
	fontcolor()方法：为字符串指定色,返回字符串
	sub()方法： 将字符串显示为下标,返回字符串
	sup()方法： 将字符串显示为上标,返回字符串
	link(url)  为字符串对象添加超链接
	```

* Date对象

	创建对象
	```javascript
	var currentDate = new Date(); // 创建当前对象实例
	var d = new Date(1000); // 创建1970-01-01 00:00:00 000之后1000ms的对象实例
	var date1 = new Date('Oct 28,97 10:12:23'); // 创建1997-10-28 10:12:23的对象实例
	var date2 = new Date('Oct 28,2007 10:12:23'); // 创建2007-10-28 10:12:23的对象实例
	// 当参数month,date,hour,minute,second超出常规取值范围时,构造函数会自动进行转换,得到相应时间
	var date3 = new Date(2009, 4, 2); // 创建2009-04-02的对象实例
	var date4 = new Date(2009, 4, 2, 10, 20, 30, 400); // 创建2009-04-02 10:20:30 400的对象实例
	```

	属性和方法
	```
	getFullYear()                 获取年份数
	getYear()                     获取年份数
	getMonth()                    获取月份数(0~11)
	getDate()                     获取日期数
	getDay()                      获取星期数(0~6)
	getHours()                    获取小时数
	getMinutes()                  获取分钟数
	getSeconds()                  获取秒数
	getMilliseconds()             获取毫秒数
	getTime()                     获取毫秒数(1970-01-01至今)
	setFullYear(yyyy, MM, dd)     设置具体日期
	setDate(date)                 设置日期
	```

* Array对象(支持数组嵌套,不支持多维数组)

	Array对象只有1个length属性,表示数组元素个数,该属性可读可写

	若数组元素不连续,则length属性为元素最大索引加1

	创建对象
	```javascript
	// 方式1
	var arr1 = [];
	arr1.push(1);
	// 方式2
	var arr2 = new Array(3);
	arr2[0] = 2;
	// 方式3
	var arr3 = new Array(3, 4, 5);
	```

	属性和方法
	```
	contact(array)                 合并
	join(separator)                是用分隔符是字符连接成字符串,默认分隔符','
	sort(sortby)                   排序
	sortby排序规则为一个比较函数,该函数要比较两个值,然后返回一个用于说明这两个值的相对顺序的数字.
	比较函数应该具有两个参数a和b,其返回值如下:
	若a小于b,在排序后的数组中a应该出现在b之前,则返回1个小于0的值;
	若a等于b则返回0.
	若a大于b,则返回一个大于0的值
	reverse()                      元素反转
	push(element)                  追加
	pop()                          删除最后1个元素,数组长度减1;对空数组,不进行任何操作,返回undefined
	shift()                        删除第1个元素
	delete array[num]              删除某个元素,数组长度不变
	unshift(e1, e2, ..., eN)       向数组首部添加1个或多个元素
	slice(start, end)              选取从start开始end结束的元素;end不指定,选取从start开始到数组结束的元素;end为负数,从数组尾部开始算起
	splice(index, howmany, item1, ..., itemX) 从数组index处删除/添加howmany个元素,howmany为0,不删除元素
	toSource()                     数组对象的源码,仅FireFox支持
	toString()                     转换为字符串
	toLocaleString()               转换为本地格式字符串
	valueOf()                      返回数组对象原始值
	```

* Math对象

	```
	round(number)                  四舍五入
	random()                       取0~1之间随机数
	max(number1, number2,..)       取最大值
	min(number1, number2,..)       取回最小值
	abs(number)                    取回绝对值
	ceil(number)                   向上取整
	floor(number)                  向下取整
	pow(a, b)                      a的b次方
	```

* Number对象

	创建对象
	```javascript
	var num1 = new Number(12);
	var num2 = new Number(.9);
	var num3 = new Number(3.9);
	var num4 = new Number('1.9');
	var num5 = new Number('23sfs');
	var num6 = new Number(undefined);
	```
	属性和方法
	```
	MAX_VALUE                      最大数
	MIN_VALUE                      最小数
	NaN                            非数字值
	NEGATIVE_INFINITY              负无穷大
	POSITIVE_INFINITY              正无穷大
	toString(radix)                转为字符串,默认基数为10,基数范围2~36
	toLocaleString()               转为字符串,使用本地格式
	toFixed(num)                   转为字符串,结果保留num位小数,默认0位,位数0~20位
	toExponential(num)             转为指数计数法,小数点num位,默认不限制小数位数,位数0~20位
	toPrecision(num)               值超出num位指定位数时将其转换为指数计数法,默认toString(),位数1~21
	valueOf()                      获取Number对象的数字值
	```

* RegExp对象

	创建对象
	```javascript
	/**
	 * g 全局匹配, i忽略大小写, m多行匹配
	 */
	var regex1 = new RegExp('a\d', 'g');
	var regex2 = /a\d/g;
	```
	属性和方法

	```
	global                         是否具有标志g
	ignoreCase                     是否具有标志i
	multiline                      是否具有标志m
	lastIndex                      下次匹配的起始位置,不具有全局匹配的RegExp对象无该属性
	source                         正则表达式的源文本
	exec(str)                      匹配字符串,返回一个数组
	test(str)                      是否匹配字符串
	compile(regex, modifier)       用于在脚本执行过程中编译,改变和重新编译正则表达式
	```

* Boolean对象

	创建对象
	```javascript
	// 对象值为true
	var t1 = new Boolean(true);
	var t2 = new Boolean('true');
	// 对象值为false
	var f1 = new Boolean();
	var f2 = new Boolean(false);
	var f3 = new Boolean('');
	var f4 = new Boolean(0);
	var f5 = new Boolean(null);
	var f6 = new Boolean(NaN);
	var f7 = new Boolean(undefined);
	```

	属性和方法
	```
	toString()                     转换为字符串
	valueOf()                      获取Boolean对象的布尔值
	```

##### BOM

* window对象:当前浏览器窗口

	```
	全局变量是window对象的属性,全局函数是window对象的方法
	innerHeight                    浏览器窗口颞部高度
	innerWidth                     浏览器窗口内部宽度
	document                       文档对象
	history
	navigator
	location
	screen
	open(url, windowName, height, width, top, left)打开窗口
	close()                        关闭窗口
	alert(string)                  弹窗提示
	confirm(string)                确认框
	prompt(string, inputContent)   输入框
	setInterval(code, milliSeconds)隔一段时间毫秒数执行一段JS代码
	clearInterval(id_of_setinterval)清除setInterval的行为
	setTimeout(code, milliSeconds) 一段毫秒数后执行一次一段JS代码
	clearTimeout(id_of_settimeout) 清除一段毫秒数后执行一次一段JS代码
	```

* history对象

	```
	back()                         后退
	forward()                      前进
	go(number)                     进入某个页面
	```

* location对象

	```
	hostname                       主机域名
	pathname                       当前页面路径和文件名
	port                           主机端口
	protocol                       web协议
	href                           当前页面url
	assign(url)                    加载新文档
	```

* screen对象

	```
	availWidth                     可用屏幕宽度
	availHeight                    可用屏幕高度
	height                         屏幕高度
	width                          屏幕宽度
	```

##### DOM操作(document)

* 常用的

	```
	style                            样式属性
	className                        类名
	innerHTML                        DOM的HTML文档
	innerText                        DOM的文本文档,FireFox不支持
	getElementById(id)               根据id获取元素
	getElementsByName(name)          根据name获取元素
	getElementsByTagName(tagName)    根据标签名获取元素
	getAttribute(key)                获取属性
	setAttribute(key, value)         设置属性
	body                             网页body
	documentElement                  文本元素
	clientWidth                      可见区域宽度
	clientHeight                     可见区域高度
	childNodes                       子节点
	parentNode                       父节点
	nodeType                         节点类型
	nodeName                         节点名
	write(string)                    向网页输出字符串
	createElement(tagName)           创建元素节点
	createTextNode(content)          创建内容为content的文本节点
	insertBefore(newDomObj, oldDomObj) 在某节点之前添加新节点
	appendChild(domObj)              添加子节点
	removeChild(domObj)              移除子节点
	offsetHeight                     网页高度(不含滚动条)
	offsetWidth                      网页宽度(不含滚动条)
	scrollHeight                     网页高度(含滚动条)
	scrollWidth                      网页宽度(含滚动条)
	```

* 追加:JavaScript获取各种高度和宽度

	```
	网页可见区域宽  document.body.clientWidth
	网页可见区域高  document.body.clientHeight
	网页可见区域宽  document.body.offsetWidth(包括边线的宽)
	网页可见区域高  document.body.offsetHeight(包括边线的宽)
	网页正文全文宽  document.body.scrollWidth
	网页正文全文高  document.body.scrollHeight
	网页被卷去的高  document.body.scrollTop
	网页被卷去的左  document.body.scrollLeft
	网页正文部分上  window.screenTop
	网页正文部分左  window.screenLeft
	屏幕分辨率的高  window.screen.height
	屏幕分辨率的宽  window.screen.width
	屏幕可用工作区高度  window.screen.availHeight
	屏幕可用工作区宽度 window.screen.availWidth
	 
	clientWidth 对象看到的宽度(不含边线,即border)
	scrollWidth 对象实际内容的宽度(若无padding,那就是边框之间距离;如有padding,就是左padding到右padding之间距离)
	offsetWidth 指对象自身的宽度(含边线,如滚动条的占用的宽,值会随着内容的输入而不断改变)
	
	scrollHeight 获取对象的滚动高度。  
	scrollLeft   设置或获取位于对象左边界和窗口中目前可见内容的最左端之间的距离
	scrollTop    设置或获取位于对象最顶端和窗口中可见内容的最顶端之间的距离
	scrollWidth  获取对象的滚动宽度
	offsetHeight 获取对象相对于版面或由父坐标 offsetParent 属性指定的父坐标的高度
	offsetLeft   获取对象相对于版面或由 offsetParent 属性指定的父坐标的计算左侧位置
	offsetTop    获取对象相对于版面或由 offsetTop 属性指定的父坐标的计算顶端位置
	 
	event.clientX 设置或获取鼠标指针位置相对于当前窗口的 x 坐标，其中客户区域不包括窗口自身的控件和滚动条
	event.clientY 设置或获取鼠标指针位置相对于当前窗口的 y 坐标，其中客户区域不包括窗口自身的控件和滚动条
	event.offsetX 设置或获取鼠标指针位置相对于触发事件的对象的 x 坐标
	event.offsetY 设置或获取鼠标指针位置相对于触发事件的对象的 y 坐标
	event.screenX 设置或获取获取鼠标指针位置相对于用户屏幕的 x 坐标
	event.screenY 设置或获取鼠标指针位置相对于用户屏幕的 y 坐标 
	x设置或获取鼠标指针位置相对于父文档的 x像素坐标(亦即相对于当前窗口)
	y设置或获取鼠标指针位置相对于父文档的 y像素坐标(亦即相对于当前窗口)
	
	document.documentElement.scrollTop 垂直方向滚动的值
	event.clientX+document.documentElement.scrollTop 相对文档的水平座标+垂直方向滚动的量
	要获取当前页面的滚动条纵坐标位置，用：document.documentElement.scrollTop;
	而不是：document.body.scrollTop;documentElement 对应的是 html 标签，而 body 对应的是 body 标签
	 
	以上主要指IE之中，FireFox差异如下:
	IE6.0/FF1.06+:
	clientWidth = width + padding
	clientHeight = height + padding
	offsetWidth = width + padding + border
	offsetHeight = height + padding + border
	IE5.0/5.5:
	clientWidth = width - border
	clientHeight = height - border
	offsetWidth = width
	offsetHeight = height
	(需要提一下: CSS中的margin属性,与clientWidth、offsetWidth、clientHeight、offsetHeight均无关)
	```

##### JS事件

* JS事件

	```
	onclick             单击事件
	onmouseover         鼠标经过事件
	onmouseout          鼠标移出事件
	onchange            文本内容改变事件
	onselect            文本框选中事件
	onfocus             聚焦事件
	onblur              离焦事件
	onload              网页加载事件
	onunload            网页关闭事件
	onkeydown           按下按键事件
	onkeyup             抬起按键事件
	```

* 事件流: 在页面接收事件的顺序  
	事件冒泡: 由最具体的元素接收, 然后逐级向上传播至最不具体的元素节点(文档)  
	事件捕获: 最不具体的节点先接收事件, 而最具体的节点最后接收事件

* 事件处理  
	1. HTML事件处理: 直接添加到HTML结构中
	2. DOM0级事件处理: 把一个函数赋值给一个事件处理程序属性(会被覆盖)
	3. DOM2级事件处理: (不会被覆盖)
	```
	addEventListener("type", "function", "useCapture")
	useCapture:true: 事件捕获; flase: 事件冒泡(默认)
	removeEventListener("type", "function", "useCapture")
	```
	4.IE事件处理程序
	```
	attachEvent("type", "function") // 添加事件
	detachEvent("type", "function") // 移除事件
	```
	5.兼容性代码
	```javascript
	var dom = document.getElementById("dom");
	if (dom.addEventListener) {
		dom.addEventListener("click", demo);
	}else if(dom.attachEvent) {
		dom.attachEvent("click", demo);
	}else{
		dom.onclick = demo();
	}
	function demo(){
		alert("demo");
	}
	```

* 事件对象(event): 再出发DOM事件时会产生一个对象
	1. type: 事件类型
	2. target: 事件目标
	3. stopPropagation(): 阻止事件冒泡
	4. preventDefault():  阻止事件默认行为
