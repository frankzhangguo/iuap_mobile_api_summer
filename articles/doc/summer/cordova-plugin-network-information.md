## 打开studio在左侧列表中找到config.xml文件，双击打开，选择插件选项勾选cordova-plugin-dialogs文件，并在权限选项中选择相关权限。最后保存文件。
#### 引用该插件主要是为了判断是否有网络连接和网络连接的类型。
    function checkConnection() {
				var networkState = navigator.connection.type;

				var states = {};
				states[Connection.UNKNOWN] = 'Unknown connection';
				states[Connection.ETHERNET] = 'Ethernet connection';
				states[Connection.WIFI] = 'WiFi connection';
				states[Connection.CELL_2G] = 'Cell 2G connection';
				states[Connection.CELL_3G] = 'Cell 3G connection';
				states[Connection.CELL_4G] = 'Cell 4G connection';
				states[Connection.CELL] = 'Cell generic connection';
				states[Connection.NONE] = 'No network connection';

				alert('Connection type: ' + states[networkState]);
			}

<a target='_blank' style="font-size:20px" href="https://github.com/iuapmobile/summerTest/tree/master/cordovaTest/cordovaCall">用例github下载地</a>

