### 浏览器判断

* 判断IE
```javascript
/**
 * 判断是否是IE
 */
function isIE() {
	return ("ActiveXObject" in window);
}

/**
 * 是否是IE6
 */
function isIE6() {
	// IE6不支持window.XMLHttpRequest
	return isIe() && !window.XMLHttpRequest;
 }

/**
 * 是否是IE7
 */
function isIE7() {
	// IE8+支持document.documentMode
	return isIe() && window.XMLHttpRequest && !document.documentMode;
}

/**
 * 是否是IE8
 */
function isIE8() {
	// alert(-[1,]); // IE6,7,8返回NaN, 则!NaN为true; 标准浏览器返回-1 , 则!-1为false
	return isIe() && !-[1,] && document.documentMode;
}

/**
 * jQuery判断是否是IE6~IE8
 */
function isIE6To8() {
	//在IE6~8中，该值返回的是false,所以加！
 	return !jQuery.support.leadingWhitespace;
}

/**
 * 是否是IE6~IE9
 */
function isIE6To9() {
	'use strict'
	if (this === undefined) {
		return true;
	}
	return false;
}

/**
 * 是否是IE10
 */
function isIE10() {
	'use strict'
	if (/MSIE\s+10.0/i.test(navigator.userAgent) && this===undefined) {
		return true;
	}
	return false;
}
```

* 判断其他类型的浏览器
```javascript
//检测函数
var check = function(r) {
	return r.test(navigator.userAgent.toLowerCase());
};

var statics = {
	/**
	 * 是否为webkit内核的浏览器
	 */
	isWebkit : function() {
		return check(/webkit/);
	},
	/**
	 * 是否为Fire Fox
	 */
	isFirefox : function() {
		return check(/firefox/);
	},
	/**
	 * 是否为Chrome
	 */
	isChrome : function() {
		return !statics.isOpera() && check(/chrome/);
	},
	/**
	 * 是否为Opera
	 */
	isOpera : function() {
		return check(/opr/);
	},
	/**
	 * 检测是否为Safari
	 */
	isSafari : function() {
		// google chrome浏览器中也包含safari
		return !statics.isChrome() && !statics.isOpera() && check(/safari/);
	}
};
```





