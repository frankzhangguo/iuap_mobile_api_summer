**目录**

[TOC]

# $scanner
是提供二维码扫描的服务对象

## $scanner.open()
打开二维码扫描

**代码演示**
```javascript
$scanner.open({
	callback : function (arges){
		var qq =args  // 返回值 object类型   key值为result
	}
})
```

## $scanner.generateQRCode()
把字符串生成二维码

**代码演示**
```javascript
var twocodepath=$scanner.generateQRCode({
	size : 30,//二维码正方形的宽高
	content : "text"//生成二维码所需的源文字
});
//返回类型string,是图片路径
$('.pic').attr('src',twocodepath)
```


<a target='_blank' style="font-size:20px" href="https://github.com/iuapmobile/summerTest/tree/master/xServiceTest/qScanner">用例github下载地</a>
