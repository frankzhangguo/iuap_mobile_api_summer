## 打开studio在左侧列表中找到config.xml文件，双击打开，选择插件选项勾选cordova-plugin-device-orientation文件，并在权限选项中选择相关权限。最后保存文件。
## 定位装置
###summer框架中的联系可以使用cordova插件(cordova-plugin-device-orientation)，主要功能包含：    
####1、获取罗盘信息                   
    function onSuccess(heading) {
	    alert('Heading: ' + heading.magneticHeading); //磁航向
	};
	
	function onError(error) {
	    alert('CompassError: ' + error.code);
	};	
    navigator.compass.getCurrentHeading(onSuccess, onError); //获取罗盘信息

####2、查看罗盘信息                   
    function onSuccess(heading) {
	    var element = document.getElementById('heading');
	    element.innerHTML = 'Heading: ' + heading.magneticHeading; //磁航向
	};
	
	function onError(compassError) {
	    alert('Compass error: ' + compassError.code);
	};
	
	var options = {
	    frequency: 3000  // Update every 3 seconds
    }; 
    watchID = navigator.compass.watchHeading(onSuccess, onError, options);//查看罗盘信息

####3、清除罗盘信息                   
    navigator.compass.clearWatch(watchID);//清除罗盘信息

<a target='_blank' style="font-size:20px" href="https://github.com/iuapmobile/summerTest/tree/master/cordovaTest/qDeviceOrientation">用例github下载地</a>

<a target='_blank' style="font-size:20px" href="https://www.npmjs.com/package/cordova-plugin-device-orientation">更多参见</a>
