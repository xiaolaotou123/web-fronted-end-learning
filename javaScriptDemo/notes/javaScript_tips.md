### js技巧代码

* 1.文本框焦点问题
```
onblur: 离焦事件
onfocus: 聚焦事件
onchange: 文本值改变时触发事件
onselect: 文本选中时触发事件
```
```javascript
<h5>点击时文字消失，失去焦点时文字再出现</h5>
<input type="text" value="example" onfocus="if (value=='example') {value=''}" onblur="if (value=='') {value='example'}"/>
```

* 2.鼠标移入移出时颜色变化
```javascript
<input type="button" value="找吧" onmouseout="this.style.color='blue'" onmouseover="this.style.color='red'"/>
```

* 3.平面按钮
```javascript
<input type="submit" name="submit" value="订阅" style="border:1px solid #666666; height:17px; width:25pt; font-size:9pt; background-color:#e8e8ff; color:#666666"/>
```

* 4.按钮颜色变化
```javascript
<input type="text" name="nick" style="border:1px solid #666666; font-size:9pt; height:17px;
background-color:#f4f4ff; color:#ff6600;" size="15" maxlength="16"/>
```

* 5.平面输入框
```javascript
<input type="text" size="20" style="border-style:solid; border-width:1;"/>
```

* 6.使窗口变成指定的大小
```javascript
window.resizeTo(300,283);
```

* 7.使文字上下滚动
```javascript
<marquee direction="up" scrollamount="1" scrolldelay="100" onmouseover="this.stop()" onmouseout="this.start()"
height="60">
<!-- head_scrolltext -->
这是文字
<!-- end head_scrolltext -->
</marquee>
```

* 8.状态栏显示该页状态
```javascript
<base onmouseover="window.status='显示网站状态'; return true"/>
```

* 9.可以点击文字实现radio选项的选定
```javascript
<input type="radio" name="regtype" value="A03" id="A03"/><label for="A03">情侣: 一次注册两个帐户</label>
```
* 10.将按钮的特征改变
```javascript
<style type="text/css">
	.style1 {
		font-size: 12px;
		background: #ccccff;
		border-width: thin thin thin thin;
		border-color: #ccccff #cccccc #cccccc #ccccff;
	}
	.style2 {
		font-size: 12px;
		font-weight: bold;
		background: #ccffcc;
		border-width: thin medium medium thin;
		border-color: #ccff99 #999999 #999999 #ccff99;
	}
</style>
<input type="submit" value="提交" onmouseover="this.className='style2'" onmouseout="this.className='style1'" class="style1"/>
```
* 11.改变按钮的图片
```javascript
<style type="text/css">
	.style3 {
		font-size: 12px;
		background: url(image/buttonbg1.gif);
		border: 0px;
		width: 60px;
		height: 22px
	}
	.style4 {
		font-size: 12px;
		font-weight: bold;
		background: url(image/buttonbg2.gif);
		border: 0px 0;
		width: 60px;
		height: 22px
	}
</style>
<input type="submit" value="提交" onmouseover="this.className='style4'" onmouseout="this.className='style3'" class="style3"/>
```
* 12.转至目标url
```javascript
<script type="text/javascript">
	window.location="http://baidu.com";
</script>
```
* 13.传递该object的form
```javascript
updateSN('guoqiang99267',this.form)
function updateSN(strValue,strForm) {
	strForm.SignInName.value = strValue;
	return false;
}
```
* 14.文字标签
```javascript
<label for="AltName4">
	<input name="AltName" type="radio" tabindex="931" id="AltName4">
	guoqiang99859
</label>
```
* 15.点击链接打印网页
```javascript
<a href='javascript:window.print()'></a>
```
* 16.显示文档最后修改日期
```javascript
function hi(str) {
	document.write(document.lastModified);
	alert("hi"+str+"!");
}
```
* 17.可以在鼠标移到文字上时就触发事件
```javascript
<script type="text/javascript">
	function hello() {
		alert("foo");
	}
</script>
<a href="#" onmouseover="hello()">link</a>
```
* 18.可以根据网页上的选项来确定页面颜色
```javascript
<html>
<head>
 <title>background.html</title>
</head>
<script type="text/javascript">
	function bgChange(selObj) {
		newColor = selObj.options[selObj.selectedIndex].text;
		document.bgColor = newColor;
		selObj.selectedIndex = -1;
	}
</script>
<body style="font-family:Arial">
	<b>Changing Background Colors</b><br/>
	<form>
		<select size="8" onChange="bgChange(this)">
			<option>red</option>
			<option>orange</option>
			<option>yellow</option>
			<option>green</option>
			<option>blue</option>
			<option>indigo</option>
			<option>violet</option>
			<option>white</option>
			<option>pink</option>
		</select>
	</form>
</body>
</html>
```
* 19.控制组件是否可见(layer2为组件id)
```javascript
	document.all.item('Layer2').style.display = "block";
	document.all.item('Layer2').style.display = "none";
```
* 20.将页面加入favorite中
```javascript
///<summary>Add the page to my favorite</summary>
///<param name="url" type="string">website address</param>
///<param name="title" type="string">site name</param>
function AddMyFavorite(url, title){
	window.external.AddFavorite(url,title);
}
```
* 21.点击value非空的选项时转向指定连接
```javascript
<select onchange="if (this.value != '') window.open(this.value)">
	<option selected>主办单位</option>
	<option>-----------------</option>
	<option value="http://www.bjd.com.cn/">北京日报</option>
	<option value="http://www.ben.com.cn/">北京晚报</option>
</select>
```
* 22.改变背景颜色
```javascript
<td bgColor="#fafbfc" onmouseover="this.bgColor='#ffffff'" onmouseout="this.bgColor='#fafbfc'"></td>
```
* 23.改变文字输入框的背景颜色
```javascript
<style type="text/css">
	.input2 {
		background-image: url('../images/inputbg.gif');
		font-size: 12px;
		background-color: #d0dabb;
		border-top-width:1px;
		border-right-width: 1px;
		border-bottom-width: 1px;
		border-left-width: 1px
	}
</style>
<input name="content" type="text" size="47" class="input2" maxlength="50"/>
```
* 24.改变水平线的特征
```javascript
<!--
在HTML 4.01中, 不赞成使用hr元素的noshade属性; 在XHTML 1.0 Strict DTD中, 不支持此属性
-->
<hr size="0" noshade="noshade" color="#c0c0c0"/>
```
* 25.页内跳转
```javascript
<a href="#1">1</a>
<br/><br/><br/><br/><br/><br/><br/>
<a id="1">dfdf</a>
```
* 26.两个按键一起按下
```javascript
if (event.ctrlKey && event.keyCode==13) {
	// to do
}
```
* 27.将网页的按钮使能
```javascript
<script type="text/javascript">
	function foo() {
		for (var i=0; i<document.form1.elements.length; i++) {
			if (document.form1.elements[i].name.indexOf('bb') != -1) {
				document.form1.elements[i].disabled =! document.form1.elements[i].disabled;
			}
		}
	}
</script>
<form name="form1">
	<input type="button" name="aa " value="cindy" onclick="foo()"/>
	<input type="button" name="bb " value="guoguo"/>
	<input type="button" name="bb " value="guoguo"/>
</form>
```
* 28.文字移动(鼠标移入, 文字停止; 鼠标移出, 文字移动)
```javascript
<marquee scrollamount="3" onmouseover="this.stop()" onmouseout="this.start()">
</marquee>
```
* 29.双击网页自动跑
```javascript
var currentpos, timer;
function initialize() {
	timer = setInterval("scrollwindow()",1);
}
function sc() {
	clearInterval(timer);
}
function scrollwindow() {
	currentpos = document.body.scrollTop;
	window.scroll(0,++currentpos);
	if (currentpos != document.body.scrollTop) {
		sc();
	}
}
document.onmousedown = sc;
document.ondblclick = initialize;
```
* 30.转向指定网页
```javascript
//方法1
document.location = url;
//方法2
document.location.assign(url);
```
* 31.可以下载文件
```javascript
document.location.href="目标文件"
```
* 32.在网页上显示实时时间
```javascript
var clock_id;
window.onload = function() {
	clock_id = setInterval('document.form1.txtclock.value=(new Date);',1000);
}
```
* 33.可以直接在页面div内写下所需内容
```javascript
<input type="button" onclick="a1.innerHTML='<font color=red>*</font>'">
<div id=a1></div>
```
* 34.可以改变页面上的连接的格式, 使其为双线
```javascript
<!-- sample -->
<style type="text/css">
	a:link {
		text-decoration: none;
		color: #0000ff;
		font-family: 宋体;
	}
	a:visited {
		text-decoration: none;
		color: #0000ff;
		font-family: 宋体;
	}
	a:hover {
		text-decoration: underline overline;
		color: ff0000;
	}
</style>
<!-- detail -->
<style type="text/css">
	a:link {
		text-decoration: none;
		color:#0000ff;
		font-family: 宋体;
	}
	a:visited {
		text-decoration: none;
		color: #0000ff;
		font-family: 宋体;
	}
	a:hover {
		text-decoration: underline overline line-through;
		color: ff0000;
	}
	th {font-size: 9pt;}
	td {font-size: 9pt;}
	body {
		scrollbar-face-color: #a9d46d;
		scrollbar-highlight-color: #e7e7e7;
		scrollbar-shadow-color:#e7e7e7;
		scrollbar-3dlight-color: #000000;
		line-height: 15pt;
		scrollbar-arrow-color: #ffffff;
		scrollbar-track-color: #e7e7e7;
	}
	input {
		border-top-width: 1px;
		padding-right: 1px;
		padding-left: 1px;
		border-left-width: 1px;
		font-size: 9pt;
		border-left-color: #cccccc;
		border-bottom-width: 1px;
		border-bottom-color: #cccccc;
		padding-bottom: 1px;
		border-top-color: #cccccc;
		padding-top: 1px;
		height: 18px;
		border-right-width: 1px;
		border-right-color: #cccccc
	}
	div, form, option, p, td, br {
		font-family: 宋体;
		font-size: 9pt;
	}
	textarea, select {
		border-width: 1px;
		border-color: #000000;
		background-color: #efefef;
		font-family: 宋体;
		font-size: 9pt;
		font-style: bold;
	}
	.text {
		font-family: "宋体";
		font-size: 9pt;
		color: #003300;
		border: #006600 solid;
		border-width: 1px 1px 1px 1px;
	}
</style>
```
* 35.直线型输入框
```javascript
<input name="password" type="password" size="10" style="border-with:0px 0px 1px; border-bottom-style:solid; background-color:#9ceb9c"/>
```
* 36.可以将背景改为按钮性状，通过改变css改变属性
```javascript
<style type="text/css">
	.mouseoverbt {
		background-image: url(http://www.yongle.com.cn/img/btbgw64h20y.gif);
		background-repeat: no-repeat;
	}
	.mouseout {
		background-color: #e0e0e0;
	}
</style>
<td width="65" align="center" bgcolor="#e0e0e0" onmouseover="this.className='mouseoverbt'" onmouseout="this.classname='mouseout'">
	<a href="tm.asp?classid=76"><font color="#000000">录音笔</font></a>
</td>
```
* 38.以下是一个完整的显示hint的代码，其思想是当鼠标停留是将div中的内容显示在鼠标出，当鼠标移出后在将该div隐藏掉
```javascript
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.0 Transitional//EN">
<html>
<style type="text/css">
	#hint{
		width: 198px;
		border: 1px solid #000000;
		background: #99ff33;
		position: absolute;
		z-index: 9;
		padding: 6px;
		line-height: 17px;
		text-align: left;
		top: 1520px;
	}
</style>
<script type="text/javascript">
	function show_me() {
		var oSon=window.document.getElementById("hint");
		if (oSon==null) {return;}
		with (oSon) {
			innerText=guoguo.value;
			style.display = 'block';
			style.pixelLeft = window.event.clientX+window.document.body.scrollLeft+6;
			style.pixelTop = window.event.clientY+window.document.body.scrollTop+9;
		}
	}
	function hide_me() {
		var oSon = window.document.getElementById("hint");
		if (oSon == null) {return;}
		oSon.style.display = "none";
	}
</script>
<body>
<text id="guoguo" value="ga"></text>
<a href="#" onmouseover="show_me()" onmouseout="hide_me()" onmousemove="show_me()" son="hint">dfdfd</a>
<div id=hint style="display: none;"></div>
</body>
</html>
```
* 39.动态改变字体的大小
```javascript
function doZoom(size) {
  	document.getElementById('zoom').style.fontSize=size+'px';
}
/*改变弹出窗口上域的属性*/
function aa() {
	var newWindow = window.open(url);
	newWindow.document.form1.text1.value = value1;
}
```
* 40.判断是何种浏览器
```javascript
var name = navigator.appName;
if (name == "Microsoft Internet Explorer") {
	alert("IE");
} else if (name == "Netscape") {
	alert("NS");
} else if (window.opera) {
	alert('opera');
}
```
* 41.复制内容到剪切板
```javascript
function JM_cc(bb) {
	var ob = eval(‘document.form1.’+bb);
	ob.select();
	js = ob.createTextRange();
	js.execCommand("Copy");
}
```
* 42.最小化窗口
```javascript
window.blur();
```
* 43.文档的路径
```javascript
document.URL;
```
* 44.设置为主页
```javascript
function makeHome(){
	netscape.security.PrivilegeManager.enablePrivilege("UniversalPreferencesWrite");
	navigator.preference("browser.startup.homepage", location.href);
}
```
* 45.设置为收藏
```javascript
function addFav(){
	if (ie) {
		window.external.AddFavorite(location.href,'WWW.OGRISH.COM : GROTESQUE MOVIES AND PICTURES');
	}
	if (ns) {
	alert("Thanks for the bookmark!\n\nNetscape users click OK then press CTRL-D");
	}
}
```
* 46.判断cookie是否可用
```javascript
var isAvailable = navigator.cookieEnabled;
```
* 47.显示有模式的有页面的弹出窗口
```javascript
function setbgcolor_onclick() {
	var color = showModalDialog('/mailpage/compose/colorsel.html', 0, 'help=0');
	if (color != null) {
		document.compose.bgcolor.value = color;
	}
}
```
* 48.截取小数点后两位
```javascript
var a = 3454545.4454545;
var b = a.toFixed(2);
```
* 49.禁止选择页面上的文字来拷贝
```javascript
<script type="text/javascript">
	function noEffect() {
		with (event) {
		returnValue = false;
		cancelBubble = true;
		}
	return;
	}
</script>
<body onselectstart="noEffect()" oncontextmenu="noEffect()"></body>
</script>
```
* 50.屏蔽右键菜单
```javascript
oncontextmenu = 'event.returnValue = false';
```
* 51.事件禁止起泡
```javascript
event.cancelBubble = true;
```
* 52.禁止在输入框打开输入法
```javascript
<input style="ime-mode: disabled"/>
```
* 53.屏蔽汉字和空格
```javascript
<input type="text" name="txt"/>
<input type="submit" onclick="alert(!/[^ -}]|\s/.test(txt.value))"/>
```
* ~~54.用javascript判断文件是否存在~~
```javascript
<script type="text/javascript">
	function Exists(filespec) {
		if (filespec) {
		var fso;
		fso = new ActiveXObject("Scripting.FileSystemObject");
		alert(fso.FileExists(filespec));
		}
	}
</script>
选择图片 <input type="file" name="f1" /><br/>
<input type="submit" onclick="Exists(f1.value)">
```
* 55.获得当前的文本框选中的文字
```javascript
<input onmouseup="alert(document.selection.createRange().text)" value="123"/>
```
* 56.跳转至目标页面, 同时不可返回
```javascript
<a href="javascript:location.replace('http://www.sohu.com/')">sohu.com</a>
```
* 57.获得当前的行是表格的第几行
```javascript
<script type="text/javascript">
	function getrow(obj) {
		if (event.srcElement.tagName == 'td') {
			curRow=event.srcElement.parentElement;
			alert('这是第'+(curRow.rowIndex+1)+'行');
		}
	}
</script>
<table border="1" width="100%" onclick="getrow(this)">
	<tr>
		<td width="20%">　</td>
		<td width="20%">　</td>
		<td width="20%">　</td>
		<td width="20%">　</td>
		<td width="20%">　</td>
	</tr>
	<tr>
		<td width="20%">　</td>
		<td width="20%">　</td>
		<td width="20%">　</td>
		<td width="20%">　</td>
		<td width="20%">　</td>
	</tr>
</table>
```
* 58.删除表格某行(xx表示某行, 下标从0开始)
```javascript
document.all.myTable.deleteRow(xx);
```
* 59.动态的向表格中添加行
```javascript
function add() {
	t1.insertRow().insertCell().innerHTML = '<input name="test'+t1.rows.length+'"/>';
}
<table id="t1" border="1"></table>
```
* 60.event.x,event.clientX,event.offsetX区别
```
x: 设置或者是得到鼠标相对于目标事件的父元素的外边界在x坐标上的位置
clientX: 相对于客户区域的x坐标位置，不包括滚动条，就是正文区域
offsetx：设置或者是得到鼠标相对于目标事件的父元素的内边界在x坐标上的位置
screenX: 相对于用户屏幕
```
* 61.显示是鼠标按钮的哪个
```javascript
<body onmousedown="alert(event.button)">点Mouse看看</body>
```
* 62.当前屏幕的分辨率
```javascript
<script type="text/javascript">
	var width = screen.width;
    var height = screen.height;
</script>
```
* 63.设置表格中的内容
```javascript
<script type="text/javascript">
	tbl.rows[0].cells[1].innerText=document.form.text1.value;
</script>
```
* ~~64.IE菜单~~
```javascript
<input type="button" value="创建新连接" onclick="document.execCommand('CreateLink','true','true')"/>
<input type="button" value="打印" onclick="document.execCommand('print','true','true')"/>
<input type="button" value="另存为htm" onclick="document.execCommand('saveas','true','网站制作.htm')"/>
<input type="button" value="另存为txt" onclick="document.execCommand('saveas','true','网站制作.txt')"/>
<input type="button" value="保存为" onclick="document.execCommand('SaveAs')"/>
<input type="button" value="撤销上一次操作" onclick="document.execCommand('undo')"/>
```
* 65.web对话框
```javascript
<script type="text/javascript">
	var contents='<style>body, td{font:menu;}img{cursor:hand;}</style>';
	contents+='<title>你要关闭我吗</title>';
	contents+='<body bgcolor="menu">';
	contents+='<table width="100%" height="100%" border="0">';
	contents+='<tr><td align="center">';
	contents+='你要关闭我吗？<br>';
	contents+='<img src="dark.gif" onclick="self.close()" alt="...关闭">';
	contents+='<img src="jet.gif" onclick="self.close()" alt="全是关闭">';
	contents+='</td></tr></table>';
	showModalDialog("about:"+contents+"","","dialogHeight:50px; dialogWidth:250px; help:no; status:no;");
	document.write(contents);
</script>
```
* 66.取第x,y的值
```javascript
<button onclick="t1.rows[x].cells[y].innerText='guoguo'">取第x,y的值</button>
```
* 67.向新打开的网页上写内容
```javascript
<script type="text/javascript">
	newWindow = window.open('about:blank','','top=10');
	newWindow.document.write('');
</script>
```
* 68.将页面上选中的内容复制到剪贴板
```javascript
abcdefg
<input type='button' onclick="window.clipboardData.setData('text',document.selection.createRange().text);" value='复制页面选中的字符'/>
```
* 69.将页面上选中的内容复制到剪贴板
```javascript
<input type="text" value="kjhkjhkhkj"/>
<input type="button" onclick="document.execCommand('Copy', 'false', null)"/>
```
* 70.鼠标移到下拉框时自动全部打开
```javascript
<select onmouseover="this.size=this.length" onmouseout="this.size=1">
	<option>1</option>
	<option>2</option>
	<option>3</option>
</select>
```
* 71.获得本机的文件
```javascript
<script type="text/javascript">
	var fso = new ActiveXObject("Scripting.FileSystemObject");
	var f1 = fso.GetFile("C:\\bsitcdata\\ejbhome.xml");
	alert("File last modified: " + f1.DateLastModified);
</script>
```
* 72.判断客户端是否是IE浏览器
因为 document.all 是 IE 的特有属性，所以通常用这个方法来判断客户端是否是IE浏览器 ,document.all?1:0;
* 73.创建新的下拉框选项
```javascript
<script type="text/javascript">
	new Option(text,value);
</script>
```
* 74.是一个特殊的容器, 想装个网页都行
```javascript
<button><iframe src="http://www.baidu.com/"></iframe></button>
```
* 75.外部的html代码
```javascript
<script type="text/javascript">
	event.srcElement.outerHTML
</script>
```
* 76.标识当前的IE事件的触发器
```javascript
<script type="text/javascript">
	event.srcElement和event.keyCode
</script>
```
* 77.事件类型
```javascript
<script type="text/javascript">
	event.type
</script>
```
* 78.动态改变类型
```javascript
<style style="text/css">
	.Overnone{
		border-width: 0;
		background-color: darkblue;
		color: gold;
		width: 115px;
	}
	.Outnone{
		border-width: 0;
		background-color: white;
		width:115px;
	}
</style>
<input class="Outnone" onmouseover="this.className='Overnone'"/>
```
* 77.页面翻转
```javascript
<html dir="rtl"></html>
```
* 78.滚屏
```javascript
<script type="text/javascript">
	parent.scroll(x,y);
</script>
<body onload="s=0" ondblclick="s=setInterval('scrollBy(0, 1)',10)" onclick="clearInterval(s)"/>
```
* 79.改变状态栏
```javascript
self.status = '';
```
* 80.改变窗口大小
```javascript
window.resizeTo(200,300);
```
* 81.背景透明
```javascript
<input type="button" value="Button" style="background-color:transparent; border:0;"/>
```
* 82.鼠标为等待形状
```javascript
<input type="button" onclick="this.style.cursor='wait'"/>
```
* 83.调用父窗口的函数
```javascript
opener.fucntion1();
```
* 84.body的内部html代码
```javascript
<input type="button" onclick="alert(code.document.body.innerHTML)" value="查看"/>
```
* 85.交换节点
```javascript
<table width="200" height="200">
	<tr><td id="c1">CELL_1</td></tr>
	<tr><td id="c2">CELL_2</td></tr>
</table>
<br/>
<input type="button" value="swap_row" onclick="c1.swapNode(c2)"/>
```
* 86.删除节点
```javascript
<table width="200" height="200">
	<tr id="trall">
		<td id="c1">CELL_1</td>
	</tr>
	<tr>
		<td id="c2">CELL_2</td>
	</tr>
</table>
<br/>
<input type="button" value="delete_row" onclick="trall.removeNode(c2)"/>
```
* 87.添加节点
```
addNode()
```
* 88.获得事件的父与子标签
```
获取子标签: event.srcElement.children[0]
获取父标签: event.srcElement.parentElement
```
* 88.判断是左键,滚轮还是右键被按下
```javascript
<body onmousedown="if (event.button==0) alert('左键');if (event.button==0) alert('滚轮');if (event.button==2) alert('右键')"></body>
```
* 89有关浏览器信息的获取
```
浏览器名称为: navigator.appName
浏览器版本为: navigator.appVersion
浏览器的代码名称为: navigator.appCodeName
用户代理标识为: navigator.userAgent
可使用的mine类型信息为: navigator.mineTypes
可使用的插件信息为: navigator.plugins
语言设定为: navigator.languages
* 90.alt/ctrl/shift键按下
event.altKey //按下alt键
event.ctrlKey //按下ctrl键
event.shiftKey //按下shift键
```
* 91.将当前位置定位为C盘
```javascript
window.location = 'C:';
```
* 92.返回输入框的类型
```
event.srcElement.type
```
* 93.模拟控件的单击事件
```javascript
<script type="text/javascript">
	function haha(){
		alert();
	}
	guoguo.click();
</script>
<input type="hidden" name="guoguo" onclick="haha()"/>
```
* 94.格式化数字
```javascript
function format_number(str, digit) {
	if (isNaN(str)) {
		alert("您传入的值不是数字！");
		return 0;
	} else if (Math.round(digit)!=digit) {
		alert("您输入的小数位数不是整数！");
		return 0;
	} else {
		return Math.round(parseFloat(str)*Math.pow(10,digit))/Math.pow(10,digit);
	}
}
```
* 95.回车按钮转化为Tab按钮
```javascript
if (event.keyCode==13) {
	event.keyCode = 9;
}
```
* 96.滚动条滚动
```javascript
text1.scrollTop = text1.scrollHeight
```
* 97.取消文本框自动完成功能
```javascript
<input type="text" autocomplete="off"/>
```
* ~~98.显示本地计算机信息~~
```javascript
var WshNetwork = new ActiveXObject("WScript.Network");
alert("Domain = " + WshNetwork.UserDomain);
alert("Computer Name = " + WshNetwork.ComputerName);
alert("User Name = " + WshNetwork.UserName);
```
* 99.弹出鼠标所在处的链结地址
```javascript
<body onmouseover="if (event.srcElement.tagName == 'a') alert(event.srcElement.href)">
<a href="http://51js.com/viewthread.php?tid=13589" >dddd</a>
<input type="text"/>
</body>
```
* 100.给类定义新的方法
```javascript
function trim_1() {
	return this.replace(/(^\s*)|(\s*$)/g, '');
}
String.prototype.trim=trim_1;
alert('cindy'.trim());
```
* 101.定义一个将日期类型转化为字符串的方法
```javascript
function guoguo_date() {
	var tmp1,tmp2;
	tmp1 = this.getMonth()+1+'';
	if (tmp1.length < 2) {
		tmp1 = '0'+tmp1;
	}
	tmp2 = this.getDate()+'';
	if (tmp2.length < 2) {
		tmp2 = '0'+tmp2;
	}
	return this.getYear()+"-"+tmp1+"-"+tmp2;
}
Date.prototype.toLiteString = guoguo_date;
alert(new Date().toLiteString());
```
* 102.pasta 是有四个参数的构造器,定义对象
```javascript
function pasta(grain, width, shape, hasEgg) {
	// 是用什么粮食做的(string)
	this.grain = grain;
	// 多宽(number)
	this.width = width;
	// 横截面形状（string）
	this.shape = shape;
	// 是否加蛋黄（boolean）
	this.hasEgg = hasEgg;
	//定义方法
	this.toString = aa;
}
function aa() {
	return '';
}
//定义对象构造器后, 用 new 运算符创建对象实例
var spaghetti = new pasta("wheat", 0.2, "circle", true);
var linguine = new pasta("wheat", 0.3, "oval", true);
//补充定义属性，spaghetti和linguine都将自动获得新的属性
pasta.prototype.foodgroup = "carbohydrates";
```
* 103.打印出错误原因
```javascript
try {
	alert(y); // 产生错误
} catch (e) {
	document.write(e.description); /打印 "'y' is undefined".
}
```
* 104.实现打印预览及打印
```javascript
<object classid="CLSID:8856F961-340A-11D0-A96B-00C04FD705A2" height="0" id="wb" name="wb" width="0"></object>
<input type="button" value="打印预览" onclick="wb.execwb(7,1)"/>
<input type="button" onclick="document.all.wb.ExecWB(6,1)" value="打印"/>
```
* 105.不通过form，直接通过名字引用对象
```javascript
<script type="text/javascript">
	alert(document.all.gg.value);
</script>
<input type="text" name="gg" value="aaaaa"/>
```
* 106.使鼠标滚轮失效
```javascript
document.onmousewheel = urn false;
```
* 107.创建弹出窗口
```javascript
var oPopup = window.createPopup();
var oPopupBody = oPopup.document.body;
oPopupBody.innerHTML = 'Display some <b>HTML</b> here.';
oPopup.show(100, 100, 200, 50, document.body);
```
* 108.取得鼠标所在处的对象
```javascript
var obj = document.elementFromPoint(event.x,event.y);
```
* 109.获得左边的对象
```javascript
<input type="text" name="gg"/>
<input type="text" name="bb" onclick="this.previousSibling.value='guoguo'"/>
```
* 110.定位鼠标
```javascript
document.all.hint_layer.style.left = event.x+document.body.scrollLeft+10;
document.all.hint_layer.style.top = event.y+document.body.scrollTop+10;
```
* 111.向下拉框指定位置添加项目
```javascript
document.all.selected_items.children(index).insertAdjacentElement('BeforeBegin', op);
op.text  = document.all.all_items[i].text;
op.value = document.all.all_items[i].value;
```
* 112.动态创建一个标签
```javascript
var newElem  = document.createElement('div');
newElem.id = 'hint_layer';
document.body.appendChild(newElem);
document.all.hint_layer.innerText = 'demo';
```
* 113.标题栏
```
document.title;
```
* 114.背景图片居中不动
```javascript
<style type="text/css">
	body {
		background-image: img/bgchild.jpg;
		background-position: center;
		background-repeat: no-repeat;
		background-attachment: fixed;
	}
</style>
```
* 115.设置透明效果
```
document.form.xxx.filters.alpha.opacity = number;
number>=0 && number<=100 0完全透明, 1完全不透明
```
* 116.定义方法
```javascript
var dragapproved = false;
document.onmouseup = new Function('dragapproved = false');
```
* 117.将数字转化为人民币大写形式
```javascript
function convertCurrency(currencyDigits) {
	// Constants:
	var MAXIMUM_NUMBER = 99999999999.99;
	// Predefine the radix characters and currency symbols for output:
	var CN_ZERO = "零";
	var CN_ONE = "壹";
	var CN_TWO = "贰";
	var CN_THREE = "叁";
	var CN_FOUR = "肆";
	var CN_FIVE = "伍";
	var CN_SIX = "陆";
	var CN_SEVEN = "柒";
	var CN_EIGHT = "捌";
	var CN_NINE = "玖";
	var CN_TEN = "拾";
	var CN_HUNDRED = "佰";
	var CN_THOUSAND = "仟";
	var CN_TEN_THOUSAND = "万";
	var CN_HUNDRED_MILLION = "亿";
	var CN_SYMBOL = "人民币";
	var CN_DOLLAR = "元";
	var CN_TEN_CENT = "角";
	var CN_CENT = "分";
	var CN_INTEGER = "整";
	// Variables:
	var integral; // Represent integral part of digit number.
	var decimal; // Represent decimal part of digit number.
	var outputCharacters; // The output result.
	var parts;
	var digits, radices, bigRadices, decimals;
	var zeroCount;
	var i, p, d;
	var quotient, modulus;
	// Validate input string:
	currencyDigits = currencyDigits.toString();
	if (currencyDigits == '') {
		alert('Empty input!');
		return '';
	}
	if (currencyDigits.match(/[^,.\d]/) != null) {
		alert("Invalid characters in the input string!");
		return '';
	}
	if ((currencyDigits).match(/^((\d{1,3}(,\d{3})*(.((\d{3},)*\d{1,3}))?)|(\d+(.\d+)?))$/) == null) {
		alert("Illegal format of digit number!");
		return '';
	}
	// Normalize the format of input digits:
	currencyDigits = currencyDigits.replace(/,/g, ""); // Remove comma delimiters.
	currencyDigits = currencyDigits.replace(/^0+/, ""); // Trim zeros at the beginning.
	// Assert the number is not greater than the maximum number.
	if (Number(currencyDigits) > MAXIMUM_NUMBER) {
		alert('Too large a number to convert!');
		return '';
	}
	// Process the coversion from currency digits to characters:
    // Separate integral and decimal parts before processing coversion:
    parts = currencyDigits.split('.');
    if (parts.length > 1) {
    	integral = parts[0];
    	decimal = parts[1];
    	// Cut down redundant decimal digits that are after the second.
    	decimal = decimal.substr(0, 2);
    } else {
    	integral = parts[0];
    	decimal = "";
    }
    // Prepare the characters corresponding to the digits:
    digits = new Array(CN_ZERO, CN_ONE, CN_TWO, CN_THREE, CN_FOUR, CN_FIVE, CN_SIX, CN_SEVEN, CN_EIGHT,CN_NINE);
    radices = new Array("", CN_TEN, CN_HUNDRED, CN_THOUSAND);
    bigRadices = new Array("", CN_TEN_THOUSAND, CN_HUNDRED_MILLION);
    decimals = new Array(CN_TEN_CENT, CN_CENT);
    // Start processing:
    outputCharacters = "";
    // Process integral part if it is larger than 0:
    if (Number(integral) > 0) {
    	zeroCount = 0;
    	for (i = 0; i < integral.length; i++) {
    		p = integral.length - i - 1;
    		d = integral.substr(i, 1);
    		quotient = p / 4;
    		modulus = p % 4;
    		if (d == "0") {
    			zeroCount++;
    		} else {
    			if (zeroCount > 0) {
					outputCharacters += digits[0];
				}
				zeroCount = 0;
				outputCharacters += digits[Number(d)] + radices[modulus];
			}
			if (modulus == 0 && zeroCount < 4) {
				outputCharacters += bigRadices[quotient];
			}
		}
		outputCharacters += CN_DOLLAR;
    }
    // Process decimal part if there is:
    if (decimal != "") {
		for (i=0; i<decimal.length; i++) {
			d = decimal.substr(i, 1);
			if (d != "0") {
				outputCharacters += digits[Number(d)] + decimals[i];
			}
		}
	}
	// Confirm and return the final output string:
	if (outputCharacters == "") {
		outputCharacters = CN_ZERO + CN_DOLLAR;
	}
	if (decimal == "") {
    	outputCharacters += CN_INTEGER;
	}
    outputCharacters = CN_SYMBOL + outputCharacters;
	return outputCharacters;
}
```
* 118.动态修改CSS的另一种方式
```javascript
this.runtimeStyle.cssText = "color:#990000; border:1px solid #cccccc;";
```
* 120.设置和使用cookie
```javascript
function setCookie() {
	var then = new Date();
	then.setTime(then.getTime() + 60*1000 ) // 60秒
	document.cookie = 'Cookie1=' + inputCookieVal.value + ';expires=' + then.toGMTString();
}
function getCookie() {
	var cookieString = new String(document.cookie)
	var cookieHeader = "Cookie1="
	var beginPosition = cookieString.indexOf(cookieHeader)
	if (beginPosition != -1) {
		document.all.Textbox.value = cookieString.substring(beginPosition  + cookieHeader.length)
	} else {
		document.all.Textbox.value = "Cookie 未找到!"
	}
}
设置与读取 cookies...<br/>
写入cookie的值<input type="text" name="inputCookieVal"/>
<input type="button" value="设置cookie" onclick = "setCookie()"/>
<input type="button" value="读取cookie" onclick = "getCookie()"/><br/>
<input type="text" name="Textbox"/>
```
* 121.显示带边框的集
```javascript
<fieldset style="border:1px gray solid;width:100px">
	<legend>查询条件</legend>
	如果周围没有边框, 说明您的浏览器太老了
</fieldset>
```
* 122.自动关闭网页
```javascript
<script type="text/javascript">
	setTimeout('window.close();', 10000); //10秒后关闭
</script>
<p align="center">本页10秒后自动关闭,请注意刷新页面</p>
```
* 122.图片加载失败时重新加载图片
```javascript
<img src="aa.gif" onerror="this.src='aa.gif'">
```
* 123.在方法中定义全局变量
```javascript
function globalVar(script) {
	eval(script); //all navigators
	//window.execScript(script); //for ie only
}
globalVar('window.haha = "../system";');
```
* 124.16进制转换成10进制
```javascript
var n = parseInt('2AE',16);
```
* 125.显示一个对象的全部的属性和属性的值
```javascript
var a = new Object();
a.name='a1';
a.***='mail'
for (var p in a) {
	alert(p+"="+a[p]);
}
```
* 126.判断一个变量是否定义
```javascript
if (typeof(a) == "undefined") {
	alert('the  variable is undefined !');
}
```
* 127.判断一个方法是否存在
```javascript
if (typeof(foo) == "function") {
	alert('the method is exist!');
} else {
	alert('the  method is not exist!');
}
```
* 127.给下拉框分组
```javascript
<select>
	<optgroup LABEL="碱性金属">
		<option>锂 (Li)</option>
		<option>纳 (Na)</option>
		<option>钾 (K)</option>
	</optgroup>
		<optgroup LABEL="卤素">
		<option>氟 (F)</option>
		<option>氯 (Cl)</option>
		<option>溴 (Br)</option>
	</optgroup>
</select>
```
* 128.加注音/拼音
```javascript
<ruby>
	漢<rt>Kan</rt>
	字<rp>(</rp><rt>ji</rt><rp>)</rp>
</ruby>
```
* 129.将url转化为16进制形式
```javascript
var ret = '';
for (var i=0; i < str.length; i++) {
	var ch = str.charAt(i);
	var code = str.charCodeAt(i);
	if (code < 128 && ch != '[' && ch != '\'' && ch != '=') {
		ret += ch;
	} else {
		ret += "[" + code.toString(16) + "]";
	}
}
```
* 129.获得某位上的ASC码
```javascript
var s='aa';
alert(s.charCodeAt(1));
```
* 130.文字居右对齐
```javascript
<input type="text" value="123" style="text-align:right">
```
* 131.放置在页面的最右边
```javascript
<input type="text" value='bu2'  style="float:right"/>
```
* 132.全屏最大化
```javascript
	newWindow = window.open("","","scrollbars");
	if (document.all) {
	    newWindow.moveTo(0,0);
	    newWindow.resizeTo(screen.width,screen.height);
	}
```
* 134.在页面上画点
```javascript
function a(x,y,color) {
	document.write(
    	'<img border="0" style="position:absolute; left:'+(x+20)
        +'; top:'+(y+20)+'; background-color: '+color+'" width="1" height="1">');
}
```
* 135.获得对象类型
```javascript
switch (object.constructor){
case Date:
	// to do
	case Number:
	// to do
	case String:
	// to do
	case MyObject:
	// to do
	default:
	// to do
}
```
* 136.加删除线
```javascript
<s>此文本将带删除线显示</s>
```
* 137.防止链接文字折行
```javascript
document.body.noWrap = true;
```
* 138.JS中的窗口重定向
```javascript
window.navigate("http://www.sina.com.cn");
```
* 139.让网页一直在frame里面
```javascript
if (window == window.top) {
	document.body.innerHTML = '<center><h1>请通过正常方式访问本页面！</h1></center>';
	//window.close();
}
```
* 140.打开新的窗口并将新打开的窗口设置为活动窗口
```javascript
var newWindow = window.open("xxxx");
newWindow.focus();
```
* 141.动态设置事件, 带参数
```javascript
<script type="text/javascript">
	function hah(para) {
		alert(para)
	}
	a1.onclick = function() {
		hah('canshu ')
	}
	//a1.attachEvent("onclick",function(){hah('参数')});
</script>
<input type="text" name="a1"/>
```
* 142.取frame中的event事件
```javascript
document.frames('workspace').event.keyCode;
```
* 142.是弹出方法的定义
```javascript
String.prototype.trim = function() {
	return this.replace(/(^\s*)|(\s*$)/g, '');
}
alert('  '.trim)
```
* 143.防止网页被包含
```javascript
if (window != window.top) {
	top.location.href = location.href;
}
```
* 144.容错脚本
```
JS中遇到脚本错误时不做任何操作:window.onerror = doNothing;
指定错误句柄的语法为:window.onerror = handleError
function handleError(message, URI, line) {// 提示用户，该页可能不能正确回应
	return true; // 这将终止默认信息
}//在页面出错时进行操作
```
* ~~145.javascript执行本机的可执行程序,需设置为可信或者降低IE安全级别~~
```javascript
<script type="text/javascript">
function exec (command) {
    window.oldOnError = window.onerror;
    window._command = command;
    window.onerror = function (err) {
      if (err.indexOf('utomation') != -1) {
        alert('命令已经被用户禁止！');
        return true;
      }
      else return false;
    };
    var wsh = new ActiveXObject('WScript.Shell');
    if (wsh)
      wsh.Run(command);
    window.onerror = window.oldOnError;
  }
</script>
调用方式
<a href="javascript:" onclick="exec('D:/test.bat')">测试</a>
```
* 146.模式窗口
```
父窗口
var url="aaa.jsp";
var data=showModalDialog(url,null,"dialogHeight:400px;dialogHeight:600px;center:yes;help:No;status:no;resizable:Yes;edge:sunken");
if(data)
 alert(data.value);
子窗口
var data=new Object();
data.value1="china";
window.returnValue=data;
window.close();
```
* 147.通过style来控制隔行显示不同颜色
```javascript
<style>
	tr{
		bgcolor:expression(this.bgColor=((this.rowIndex)%2==0 )? 'white' : 'yellow');
	}
</style>
<table id="oTable" width="100" border="1" style="border-collapse:collapse;">
	<tr><td> </td></tr>
	<tr><td> </td></tr>
	<tr><td> </td></tr>
	<tr><td> </td></tr>
	<tr><td> </td></tr>
</table>
```
* 149.复制粘贴
```javascript
<script type="text/javascript">
	function cpyAndPst() {
		clipboardData.setData("Text",a1.value
		aa.innerText=clipboardData.getData("Text");
	}
</script>
<input type="file" name='a1'>
<input type="button" value='复制粘贴' onclick="cpyAndPst()">
<div id="aa"></div>
```
* 150.弹出新页面，关闭旧页面，不弹出提示框
```javascript
var w = screen.availWidth-10;
var h = screen.availHeight-10;
var swin=window.open("/mc/mc/message_management.jsp","BGSMbest","scrollbars=yes,status,location=0,menubar=0,toolbar=0,rizable=no,top=0,left=0,height="+h+",width="+w);
window.opener = null;
window.close();
```
* ~~150.加为首页~~
```javascript
<script type="text/javascript">
	function fnSet(){
		oHomePage.setHomePage(location.href);
		event.returnValue = false;
	}
</script>
<IE:HOMEPAGE id="oHomePage" style="behavior:url(#default#homepage)"/>
```
* ~~152.xmlhttp技术~~
```javascript
<script type="text/javascript">
	function getDatal(url){
		var xmlhttp = new ActiveXObject("Microsoft.XMLHTTP"); // 创建XMLHTTPRequest对象
		xmlhttp.open("GET",url,false,"",""); // 使用HTTP GET初始化HTTP请求
		xmlhttp.send(""); // 发送HTTP请求并获取HTTP响应
		return xmlhttp.responseXML; // 获取XML文档
	}
</script >
<body> 此方法是通过XMLHTTP对象从服务器获取XML文档，示例如下。
<input type=button value="加载XML文档" onclick="getData('data.xml')"/>
</body>
```
* 153.
```javascript
<a href="#" onclick="document.execCommand('open')">打开</a><br>
<a href="#" onclick=location.replace("view-source:"+location)>使用 记事本编辑</a><br>
<a href="#" onclick=document.execCommand("saveAs")>另存为</a><br>
<a href="#" onclick=document.execCommand("print")>打印</a><br>
<a href="#" onclick=window.close();return false)>关闭本窗口</a><br>
<a href="#" onclick=document.execCommand("selectAll")>全选</a><br>
<a href="#" onclick=location.reload()>刷新</a> <a href="#" onclick=history.go(0)>刷新</a><br>
<a href="#" onclick=location.replace("view-source:"+location)>查看源文件</a><br>
<a href="#" onclick=window.open(document.location,"url","fullscreen")>全屏显示</a><br>
<a href="javascript:window.external.AddFavorite('http://homepage.yesky.com', '天极网页陶吧')">添加到收藏夹</a><br>
<a href="#" onclick=window.external.showBrowserUI("OrganizeFavorites",null)>整理收藏夹</a><br>
<a href="#" onclick=window.external.showBrowserUI("PrivacySettings",null)>internet选项</a><br>
<a href="#" onclick=history.go(1)>前进1</a>　<a href="###" onclick=history.forward()>前进2</a><br>
<a href="#" onclick=history.go(-1)>后退1</a>　<a href="###" onclick=history.back()>后退2</a><br>
<a href="#" onclick=settimeout(window.close(),3000)>3秒关闭本窗口</a><br>
```
[innerouterheight]<http://www.runoob.com/jsref/prop-win-outerheight.html>
* 154.背景图高度自适应
```javascript
	html {
		height: 100%;
	}
	body {
		background: #FFF;
		url(../../pics.jpg) repeat-y center top;
		background-size: cover;
	}
```