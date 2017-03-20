## 打开studio在左侧列表中找到config.xml文件，双击打开，选择插件选项勾选cordova-plugin-media-capture文件，并在权限选项中选择相关权限。最后保存文件。
### 该插件提供了对设备视频、音频、图片的捕捉能力。
    var captureSuccess = function(mediaFiles) {
				var i,
				    path = '',
				    len;
				for ( i = 0, len = mediaFiles.length; i < len; i += 1) {
					path = path + mediaFiles[i].fullPath;
					// do something interesting with the file
				}
				alert(path);
			};

			// capture error callback
			var captureError = function(error) {
				navigator.notification.alert('Error code: ' + error.code, null, 'Capture Error');
			};

			function audioStart() {
				// start audio capture
				navigator.device.capture.captureAudio(captureSuccess, captureError, {
					limit : 2
				});
			}
+ **captureSuccess** 捕捉成功的回调，保存文件得路径；
+ **captureError**   捕捉失败的回调，返回失败的状态；
+ **CaptureAudioOptions** 捕捉的参数，limit表示限制的数量

<a target='_blank' style="font-size:20px" href="https://github.com/iuapmobile/summerTest/tree/master/cordovaTest/cordovaCall">用例github下载地</a>


