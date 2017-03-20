## 打开studio在左侧列表中找到config.xml文件，双击打开，选择插件选项勾选cordova-plugin-media文件，并在权限选项中选择相关权限。最后保存文件。
### 该插件提供了记录和播放音频的功能。
var media = new Media(src, mediaSuccess, [mediaError], [mediaStatus])；
+ **src：** 音频文件路径；
+ **mediaSuccess:** 音频播放完毕后执行的回调；
+ **mediaError**    发生错误时执行的回调；
+ **mediaStatus**   播放状态发生改变时的回调；

#### 示例代码
    function playAudio() {
		var my_media = new Media('http://audio.ibeat.org/content/p1rj1s/p1rj1s_-_rockGuitar.mp3',
		function() {
				console.log("playAudio():Audio Success");
			},
		function(err) {
				console.log("playAudio():Audio Error: " + err);
			});
		my_media.play();
			}

<a target='_blank' style="font-size:20px" href="https://github.com/iuapmobile/summerTest/tree/master/cordovaTest/cordovaCall">用例github下载地</a>
