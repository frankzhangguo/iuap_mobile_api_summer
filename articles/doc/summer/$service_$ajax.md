**目录**

[TOC]

#$service
与服务器服务处理

## $service.get()
以get方式向服务器索求数据的请求

**代码演示**
```javascript
$service.get({
	"url" : "http://opentest.yonyoutelecom.cn/mobile/isvName.do?account=qinfx&q=",//必选参数，get请求的URL
	"callback" : function (sender,args){
		//返回结果类型为对象，键值为resule的结果类型为json数组格式的字符串类型。
		var str=args.result;
		var arr=(eval(args.result)[1];
		var obj=eval(args.result)[1].text;
	}/*,
	"header":{
		"Content-Type":"application/x-www-form-urlencoded",//可选参数，方便开发者设置请求的header
		"User-Agent":"imgfornote"
	},
	"timeout" : "5"*//可选参数，超时时间，单位为秒
})
```

## $service.post()
以post方式向服务器索求数据的请求

**代码演示**
```javascript
$service.post({
	"url" : "http://opentest.yonyoutelecom.cn/mobile/isvName.do?account=qinfx&q=",//必选参数，post请求的URL
		"callback" : function (sender,args){
		//返回结果类型为对象，键值为resule的结果类型为json数组格式的字符串类型。
		var str=args.result;
		var arr=(eval(args.result)[1];
		var obj=eval(args.result)[1].text;
	}/*,
	"data" : {a:1,b:2},//可选参数，post请求的要写入的条件数据，须为json对象
	"header":{
		"Content-Type":"application/x-www-form-urlencoded",//可选参数，方便开发者设置请求的header
		"User-Agent":"imgfornote"
	},
	"timeout" : "5"*//可选参数，超时时间，单位为秒
})
```

<a target='_blank' style="font-size:20px" href="https://github.com/iuapmobile/summerTest/tree/master/xServiceTest/qService">用例github下载地</a>
