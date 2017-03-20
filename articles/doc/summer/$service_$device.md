**目录**

[TOC]

# $device
设备访问

## $device.getTimeZoneID()
获取时区的ID（支持Android）,返回结果为 08:00

**代码演示**
```javascript
var str =$device.getTimeZoneID()
```

## $device.getTimeZoneDisplayName()
获取时区的DisplayName,（支持Android）返回结果为 Asia/Shanghai

**代码演示**
```javascript
var str =$device.getTimeZoneDisplayName()
```

## $device.getLocation()
获取位置信息 ,返回结果为json对象 键值为location是个string类型，需要转换成json对象，对象中的longitude为经度，latitude为纬度
***此方法通过高德地图获取位置，使用时请先参照《DSL控件指南-高级-高德地图》配置应用签名-keystore***

**代码演示**
```javascript
$device.getLocation({
	"bindfield" : "location", //位置信息回写的绑定字段
	"callback" :  function(args){
		var str1 ='经度为'+JSON.parse(args.location).longitude;
		var str2 ='纬度为'+JSON.parse(args.location).latitude;
	},  //回调执行的JS方法
	"single" : "true", //是否只获取1次
	"isgetaddress" : "true", //是否需要获取地址
	"network" : "true" //是否使用wifi定位
})
```

## $device.openWebView()
打开网页,通过改变url地址跳转新的网页

**代码演示**
```javascript
$device.openWebView({
	"url" : "http://www.yyuap.com"
});
```

## $device.getInternalMemoryInfo()
获取内部存储信息 ,返回结果为json对象第一个键值为总的存储空间，第二个键值为空余存储空间

**代码演示**
```javascript
var json =$device.getInternalMemoryInfo()
```

## $device.getExternalStorageInfo()
获取外部存储信息，仅android支持，返回json类型为string key值为TotalSize、freeSize

**代码演示**
```javascript
var json =$device.getExternalStorageInfo()
```

## $device.getMemoryInfo()
获取存储信息,返回json类型为string key值为MemToal、MenFree等多个字段

**代码演示**
```javascript
var json =$device.getMemoryInfo()
```

## $device.getDeviceInfo()
获取设备信息，返回结果为json，key值为deviceid、os、screen、version等多个字段

**代码演示**
```javascript
var json =$device.getDeviceInfo ()
```

## $device.getScreenHeight()
获取手机屏幕的高度   //返回number类型

**代码演示**
```javascript
var num =$device.getScreenHeight()
```

## $device.getScreenWidth()
获取手机屏幕的宽度   //返回number类型

**代码演示**
```javascript
var num =$device.getScreenWidth()
```

## $device.getScreenDensity()
获取手机像素密度  //返回number类型

**代码演示**
```javascript
var num =$device.getScreenDensity()
```

## $device.notify()
提醒服务

**代码演示**
```javascript
$device.notify({
	"sendTime" : "2015-02-03 13:54:30",//提示时间
	"sendBody" : "您设置了消息提醒事件",//提示文字内容
	"icon" : "app.png"//图标
})
```

## $device.capturePhoto()
获取手机相册图片

**代码演示**
```javascript
$device.capturePhoto({
	"callback" : function (args){
			alert(args.imgPath)
	}
});
```

## $device.screenShot()
手机截屏服务

**代码演示**
```javascript
$device.screenShot({
	"callback" : function (args){
		alert(typeof args);
		$alert(args)
	}
})
```

## $device.saveContact()
把信息写入通讯录

**代码演示**
```javascript
$device.saveContact({  //   android 和 ios支持，
	"tel" : "139****",//手机号码
	"employeename" : "张三",//联系人名称
	"jobname" : "职员",//职位
	"orgname" : "开发部",//部门名称
	"address" : "北京市海淀区***",//单位地址
	"email" : "zhangsan@yonyou.com",//邮箱
	"officetel" : "6243****"//办公电话
})
```

## $device.openAddressBook()
打开通讯录

**代码演示**
```javascript
$device.openAddressBook();
```

## $device.getContacts()
获取手机通讯录

**代码演示**
```javascript
var qq = $device.getContacts()
```

## $device.currentOrientation()
获取手机横竖屏状态，返回值为 "portrait" | "landscape", 表示 横屏 or 竖屏

**代码演示**
```javascript
var qq = $device.currentOrientation())
```

## $device.generateQRCode()
把字符串生成二维码

**代码演示**
```javascript
var qq=$device.generateQRCode({
	 size : 30,//二维码正方形的宽高
	 content : "text"//生成二维码所需的源文字
});
```

## $device.getAlbumPath()
获取相册路径 - Android独有

**代码演示**
```javascript
var qq=$device.getAlbumPath()  //获取相册路径  返回类型为string
```

## $device.getAppAlbumPath()
获取相机服务存放照片的存储路径

**代码演示**
```javascript
var qq=$device.getAlbumPath()  //获取相册路径  返回类型为string
```

<a target='_blank' style="font-size:20px" href="https://github.com/iuapmobile/summerTest/tree/master/xServiceTest/qDevice">用例github下载地</a>


