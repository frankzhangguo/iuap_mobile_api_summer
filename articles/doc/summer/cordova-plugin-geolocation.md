## 打开studio在左侧列表中找到config.xml文件，双击打开，选择插件选项勾选cordova-plugin-geolocation文件，并在权限选项中选择相关权限。最后保存文件。
## 地理位置
###summer框架中的联系可以使用cordova插件(cordova-plugin-geolocation)，主要功能包含：    
####1、获取定位信息
```javascript
var onSuccess = function(position) {
					alert('Latitude: '          + position.coords.latitude          + '\n' +
							'Longitude: '         + position.coords.longitude         + '\n' +
							'Altitude: '          + position.coords.altitude          + '\n' +
							'Accuracy: '          + position.coords.accuracy          + '\n' +
							'Altitude Accuracy: ' + position.coords.altitudeAccuracy  + '\n' +
							'Heading: '           + position.coords.heading           + '\n' +
							'Speed: '             + position.coords.speed             + '\n' +
							'Timestamp: '         + position.timestamp                + '\n');
				};

				// onError Callback receives a PositionError object
				//
				function onError(error) {
					alert('code: '    + error.code    + '\n' +
							'message: ' + error.message + '\n');
				}

				navigator.geolocation.getCurrentPosition(onSuccess, onError);
```

<a target='_blank' style="font-size:20px" href="https://github.com/iuapmobile/summerTest/tree/master/cordovaTest/qGeolocation">用例github下载地</a>

<a target='_blank' style="font-size:20px" href="https://www.npmjs.com/package/cordova-plugin-geolocation">更多参见</a>
