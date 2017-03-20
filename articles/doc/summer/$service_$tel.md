**目录**

[TOC]

# $tel
是与电话、短信、邮件相关的服务对象

## $tel.call()
打电话

**示例代码**
```javascript
$tel.call("139***")
```

## $tel.sendMsg()
发短信服务，支持群发短信

**示例代码**
```javascript
$tel.sendMsg({
	"tel" : "139***,1397***",//电话号码
	"body" : "hello"//短信内容
})
```

## $tel.sendMail()
发邮件服务，支持群发邮件

**示例代码**
```javascript
$tel.sendMail({
	"receive" : "wwww@qq.com,lll@163.com"，//收件人
	"title" : "hello",//邮件主题
	"content" : "欢迎使用UAP Mobile"//邮件内容
})
```

<a target='_blank' style="font-size:20px" href="https://github.com/iuapmobile/summerTest/tree/master/xServiceTest/qTel">用例github下载地</a>
