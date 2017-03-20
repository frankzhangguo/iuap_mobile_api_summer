## 打开studio在左侧列表中找到config.xml文件，双击打开，选择插件选项勾选cordova-plugin-dialogs文件，并在权限选项中选择相关权限。最后保存文件。
## 对话框
###summer框架中的联系可以使用cordova插件(cordova-plugin-dialogs)，主要功能包含：    
####1、 对话框1                  
    navigator.notification.prompt('请输入你的名字', // message
	    onPrompt, // callback to invoke
	    '注册', // title
	    ['确定', '退出'], // buttonLabels
	    'iuap mobile' // defaultText
	);
	
	function onPrompt(results) {
	    alert("You selected button number " + results.buttonIndex + " and entered " + results.input1);
    }

####2、对话框2                   
    navigator.notification.alert(
	    'You are the winner!',  // message
	     alertDismissed,         // callback
	    'Game Over',            // title
	    'Done'                  // buttonName
	);
	
	function alertDismissed() {
	    alert("ok")
    }

####3、对话框3                   
    function onConfirm(buttonIndex) {
	    alert('You selected button ' + buttonIndex);
	}

	navigator.notification.confirm(
	    'You are the winner!', // message
	     onConfirm,            // callback to invoke with index of button pressed
	    'Game Over',           // title
	    ['Restart','Exit']     // buttonLabels
    );
	
```
<a target='_blank' style="font-size:20px" href="https://github.com/iuapmobile/summerTest/tree/master/cordovaTest/qDialogs">用例github下载地</a>

<a target='_blank' style="font-size:20px" href="https://www.npmjs.com/package/cordova-plugin-dialogs">更多参见</a>
