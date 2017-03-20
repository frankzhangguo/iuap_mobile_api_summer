**目录**

[TOC]

# 扩展原生服务

***需要使用原生技术，高级功能，新手勿入***

扩展服务在现有封装的服务不足以满足我们的要求时，可以通过自定义扩展服务来实现，即为平台扩展开发新的API服务。
扩展服务开发完成之后，在菜单-移动平台-扩展服务导入。

**注意**：*使用扩展服务需要在配置文件的插件页签中勾选对应的插件*。

# 扩展服务制作和管理

## 1、准备材料

**此处不讲解如何开发扩展的原生部分，开发扩展的原生部分可以参考本文的子文档（扩展开发手册和扩展SDK），假设扩展的原生部分已经开发完成**。
取Android及IOS扩展服务相关的源文件（包含原生服务、相关资源及启动文件）。

## 2、制作扩展服务

### （1）、拷贝资源
以IM_Service为例，将准备的Android扩展服务相关的源文件（包含原生服务、相关资源及启动类）拷贝到IM_Service\android目录下；IOS扩展服务相关的源文件（包含原生服务、相关资源及启动库）拷贝到IM_Service\ios目录下。

### （2）、创建配置文件
在IM_Control目录下创建名为config.xml的配置文件，为避免创建的文件编码与平台不兼容，建议从示例中直接拷贝，然后修改。如下图：
![](/portal/upload/doc/20161123/20161123160902037.png)

### （3）、编辑配置文件
```xml
<plug>
	<services type="android" name="YMCoreService">
		<import type="jar" ref="android/libs/" />
		<service method="initIMSDK" name="initIMSDK" classname="com.yonyou.sns.im.mobile.service.YMCoreService" description="IM初始化SDK">
			<arguments>
				<argument name="etpkey" type="String" description="用户的企业key" />
				<argument name="appkey" type="String" description="用户的应用key" />
				<argument name="callback" type="String" description="返回正确结果的回调处理方法" />
				<argument name="error" type="String" description="返回异常时的回调处理方法" />
				<argument name="usercontroller" type="String" description="提供用户信息的controller" />
				<argument name="tokencontroller" type="String" description="提供用户获取token的controller" />
			</arguments>
		</service>
		<service method="doLogin" name="doLogin" classname="com.yonyou.sns.im.mobile.service.YMCoreService" description="IM登陆">
			<arguments>
				<argument name="userid" type="String" description="用户id" />
				<argument name="username" type="String" description="用户的名字" />
				<argument name="callback" type="String" description="返回正确结果的回调处理方法" />
				<argument name="error" type="String" description="返回异常时的回调处理方法" />
			</arguments>
		</service>
	</services>
	<services type="android" name="YMUserService">
		<service method="getUser" name="getUser" classname="com.yonyou.sns.im.mobile.service.YMUserService" description="获得用户信息">
			<arguments>
				<argument name="userid" type="String" description="用户id" />
				<argument name="callback" type="String" description="返回正确结果的回调处理方法" />
				<argument name="error" type="String" description="返回异常时的回调处理方法" />
			</arguments>
		</service>
	</services>
	<services type="ios" name="YMCoreService">
		<import type="so" ref="ios/Framework/" obj="path"/>
		<import type="so" ref="ios/Library/" obj="path"/>
		<import type="so" ref="ios/Resource/" obj="path"/>
		<import type="so" ref="ios/Source/" obj="path"/>
		<service method="initIMSDK" classname="YMCoreService" hfile="YMCoreService.h" name="initIMSDK" description="IM初始化SDK">
			<arguments>
				<argument name="mapkey" type="String" description="IOS的申请高德地图key" />
				<argument name="apnscert" type="String" description="推送证书的名称" />
				<argument name="etpkey" type="String" description="用户的企业key" />
				<argument name="appkey" type="String" description="用户的应用key" />
				<argument name="callback" type="String" description="返回正确结果的回调处理方法" />
				<argument name="error" type="String" description="返回异常时的回调处理方法" />
				<argument name="usercontroller" type="String" description="提供用户信息的controller" />
				<argument name="tokencontroller" type="String" description="提供用户获取token的controller" />
			</arguments>
		</service>
		<service method="doLogin" classname="YMCoreService"  hfile="YMCoreService.h" name="doLogin" description="IM登陆">
			<arguments>
				<argument name="userid" type="String" description="用户id" />
				<argument name="username" type="String" description="用户的名字" />
				<argument name="callback" type="String" description="返回正确结果的回调处理方法" />
				<argument name="error" type="String" description="返回异常时的回调处理方法" />
			</arguments>
		</service>
	</services>
	<services type="ios" name="YMUserService">
		<service method="getUser" classname="YMUserService" hfile="YMUserService.h" name="getUser" description="获得用户信息">
			<arguments>
				<argument name="userid" type="String" description="用户id" />
				<argument name="callback" type="String" description="返回正确结果的回调处理方法" />
				<argument name="error" type="String" description="返回异常时的回调处理方法" />
			</arguments>
		</service>
	</services>
</plug>
```

### （4）、属性说明

**可自定义属性说明**
- services\name：服务组的名字
- import\ref：Android是指扩展的Jar包所在目录，IOS是指扩展的Source目录
- service\method：服务对应的类方法名，开发时一般Android和IOS保持一致
- service\name：服务的别名，用于在JS中调，一般和method保持一致
- service\classname：Android为服务对应的类路径，IOS为类名
- service\description：服务的描述
- service\hfile：IOS类对应的头文件，仅IOS有
- argument\name：参数的名字
- argument\description：参数的描述

**固定属性说明**
- services\type：平台类型（android表示Android；ios表示IOS）
- import\type：源类型（jar表示Android库，res表示Android资源；so表示IOS库）
- import\obj：资源类型（path表示目录，file表示文件）
- argument\type：参数的类型（一般为String）

### （5）、制作压缩文件
将以上制作的目录压缩成zip包（包名随意），如下图：
![](/portal/upload/doc/20161123/20161123161450053.png)

## 3、扩展服务管理

制作完服务后可以首选项中将服务导入、导出及删除，如下图：
![](/portal/upload/doc/20161123/20161123160443381.png)

## 4、扩展服务使用

扩展服务导入并勾选所在的插件之后，就可以在JS调用相应的服务了，代码如下：
```javascript
summer.callService("YMCoreService.initIMSDK", {
	"etpkey" : "用户的企业key",
	"appkey" : "用户的应用key",
	"usercontroller" : "提供用户信息的controller",
	"tokencontroller" : "提供用户获取token的controller",
	"callback" : "microPhoneCallback()",
	"error" : "返回异常时的回调处理方法"
}, false);

function microPhoneCallback(args) {
	var keyword = $stringToJSON(args).text;
	$alert(keyword)
}
```
- YMCoreService为服务组的名字
- initIMSDK为服务名（name和method不同时请使用name）

勾选所在的插件
![](/portal/upload/doc/20170106/20170106163631673.png)

**配置第三方Framework**
IOS扩展中如果使用了第三方Framework，则需要在ios-config.xml文件中配置framework。

文件位置如下：
![](/portal/upload/doc/20161123/20161123162631490.png)

配置内容如下：
```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<config>
	<sys-framework>
		<framework>CoreLocation.framework</framework>
		<framework>CoreTelephony.framework</framework>
	</sys-framework>
	<delegate-classes>
		<class>
		</class>
	</delegate-classes>
	<debugSettings>
		<debug>
		</debug>
		<release>
		</release>
	</debugSettings>
</config>
```

## 5、扩展示例下载
地址：https://pan.baidu.com/s/1bNm8pS
