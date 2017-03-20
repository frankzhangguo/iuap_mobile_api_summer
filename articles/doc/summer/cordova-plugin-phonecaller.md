## 打开studio在左侧列表中找到config.xml文件，双击打开，选择插件选项勾选cordova-plugin-phonecaller文件，并在权限选项中选择相关权限。最后保存文件。
## 电话
###summer框架中的联系可以使用cordova插件(cordova-plugin-phonecaller)，功能包含：    
####1、拨打电话                   
    window.PhoneCaller.call("1381051373",  //参数类型为string
	    function (arg){
		  alert(arg+'success');//成功回调 返回ok
	    }, 
	    function (arg){
		  alert(arg+'error'); //失败回调
    })


<a target='_blank' style="font-size:20px" href="https://github.com/iuapmobile/summerTest/tree/master/cordovaTest/qPhoneCaller">用例github下载地</a>

<a target='_blank' style="font-size:20px" href="https://www.npmjs.com/package/cordova-plugin-phonecaller">更多参见</a>