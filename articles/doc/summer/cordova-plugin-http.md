## 打开studio在左侧列表中找到config.xml文件，双击打开，选择插件选项勾选cordova-plugin-http文件，并在权限选项中选择相关权限。最后保存文件。
## 网络请求
###summer框架中的联系可以使用cordova插件(cordova-plugin-http)，主要功能包含：    
####1、get请求数据                   
   ```javascript
cordovaHTTP.get("http://opentest.yonyoutelecom.cn/mobile/isvName.do?account=qinfx&q=",//请求的url地址
	{    //请求的数据
		a: 1,
		b: 2
	}, {Authorization: "OAuth2: token"},//
	function (response) {//成功的回调
		// prints 200
		alert(response.status);
		try {
			response.data = JSON.parse(response.data);
			// prints test
			$summer.alert(response.data);
		} catch (e) {
			alert("JSON parsing error");
		}
	}, function (response) {//失败的回调
		// prints 403
		alert(response.status);

		//prints Permission denied
		alert(response.error);
	}
```
####2、post请求数据                   
   ```javascript
cordovaHTTP.post("http://opentest.yonyoutelecom.cn/mobile/isvName.do?account=qinfx&q=",//请求的url地址
	{//请求的数据
		a: 1,
		b: 2
	}, {Authorization: "OAuth2: token"}, 
	function (response) {//成功的回调
		// prints 200
		alert(response.status);
		try {
			response.data = JSON.parse(response.data);
			// prints test
			$summer.alert(response.data);
		} catch (e) {
			alert("JSON parsing error");
		}
	}, function (response) {//失败的回调
		// prints 403
		alert(response.status);

		//prints Permission denied
		alert(response.error);
	}
```

<a target='_blank' style="font-size:20px" href="https://github.com/iuapmobile/summerTest/tree/master/cordovaTest/qHttp">用例github下载地</a>

<a target='_blank' style="font-size:20px" href="https://www.npmjs.com/package/cordova-plugin-http">更多参见</a>
