## 打开studio在左侧列表中找到config.xml文件，双击打开，选择插件选项勾选cordova-plugin-globalization文件，并在权限选项中选择相关权限。最后保存文件。
####  改插件提供了获取全局变量的方法
###### navigator.globalization.getPreferredLanguage
  function getlanguage() {
	navigator.globalization.getPreferredLanguage(function(language) {
	        alert('language: ' + language.value + '\n');
	}, function() {
	     alert('Error getting language\n');
	});
	}
###### param
* successFun 成功的回调；
* errorFun   失败的回调。

###### navigator.globalization.getLocaleName
    function getLocalName(){
	navigator.globalization.getLocaleName(
	function (locale) {alert('locale: ' + locale.value + '\n');},
	function () {alert('Error getting locale\n');}
				);
			}
* successFun 成功的回调；
* errorFun   失败的回调。


<a target='_blank' style="font-size:20px" href="https://github.com/iuapmobile/summerTest/tree/master/cordovaTest/cordovaCall">用例github下载地</a>
