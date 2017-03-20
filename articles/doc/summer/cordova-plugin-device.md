## 设备信息
####1、获取加速计                  
   ```javascript
function openDevice() {
	var model = device.model;
	var uuid = device.uuid;
	var version = device.version;
	var platform = device.platform;
	var manufacturer = device.manufacturer;
	var serial = device.serial;
	alert("model:"+model + ",uuid:" +uuid +",version:"+version+",platform:"+platform+",manufacturer:"+manufacturer+",serial:"+serial)
}

```


<a target='_blank' style="font-size:20px" href="https://github.com/iuapmobile/summerTest/tree/master/cordovaTest/xDevice">用例github下载地</a>

<a target='_blank' style="font-size:20px" href="https://www.npmjs.com/package/cordova-plugin-device">更多参见</a>