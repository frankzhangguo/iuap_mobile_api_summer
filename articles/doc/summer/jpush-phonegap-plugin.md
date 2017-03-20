## 极光推送插件
### 配置
1. 项目中config文件夹下，打开application.properties文件，找到JPUSH_APPKEY=appkey> appkey代表的是极光推送官网上需要推送此应用生成的appkey
2. 打开config.xml文件，在插件配置勾选cordova-plugin-device和jpush-phonegap-plugin插件。
3. 打包生成。

### 用法

```

var app = {
    // Application Constructor
    initialize: function() {
        this.bindEvents();
    },
    bindEvents: function() {
        document.addEventListener('deviceready', this.onDeviceReady, false);

    },
    onDeviceReady: function() {
        app.receivedEvent('deviceready');
    },
    receivedEvent: function(id) {
        // 监听加载完成事件
        document.addEventListener("deviceready", onDeviceReady, false);
        // 设置标签和别名
        document.addEventListener("jpush.setTagsWithAlias", onTagsWithAlias, false);
        // 打开通知
        document.addEventListener("jpush.openNotification", onOpenNotification, false);
        // 获取通知内容
        document.addEventListener("jpush.receiveNotification", onReceiveNotification, false);
        // 获取自定义消息推送内容
        document.addEventListener("jpush.receiveMessage", onReceiveMessage, false);
    }
};

// 开始
var onDeviceReady = function() {
    alert("JPushPlugin:Device ready!");
    initiateUI();
};

var initiateUI = function() {
    try {
        //初始化
        window.plugins.jPushPlugin.init();
        getRegistrationID();

        if (device.platform != "Android") {
            window.plugins.jPushPlugin.setDebugModeFromIos();
            window.plugins.jPushPlugin.setApplicationIconBadgeNumber(0);
        } else {
            window.plugins.jPushPlugin.setDebugMode(true);
            window.plugins.jPushPlugin.setStatisticsOpen(true);
        }
    } catch (exception) {
        console.log(exception);
    }

    $("#setTagWithAliasButton").click(function(ev) {
        alert("点击了按钮");
        try {
            var tag1 = $("#tagText1").val();
            var tag2 = $("#tagText2").val();
            var tag3 = $("#tagText3").val();
            var alias = $("#aliasText").val();
            var tags = [];

            if (tag1 != "") {
                tags.push(tag1);
            }
            if (tag2 != "") {
                tags.push(tag2);
            }
            if (tag3 != "") {
                tags.push(tag3);
            }
            alert(tags[0]+'...'+tags[1]+"....");
            alert(alias);
            window.plugins.jPushPlugin.setTagsWithAlias(tags, alias);
        } catch (exception) {
            alert(exception);
        }
    })
};
//获取注册ID
var getRegistrationID = function() {
    window.plugins.jPushPlugin.getRegistrationID(onGetRegistrationID);
};
// 赋值ID给Dom
var onGetRegistrationID = function(data) {
    try {
        
        if (data.length == 0) {
            var t1 = window.setTimeout(getRegistrationID, 1000);
        }
        //将注册ID赋值给DOM上
        console.log("即将给最上边的label赋值ID");
        $("#registrationId").html(data);
    } catch (exception) {
        alert(exception);
    }
};
// 设置标签和别名
var onTagsWithAlias = function(event) {
    try {
        var result = "result code:" + event.resultCode + " ";
        result += "tags:" + event.tags + " ";
        result += "alias:" + event.alias + " ";
        alert("即将把tags和alias显示在页面上");
        $("#tagAliasResult").html(result);
    } catch (exception) {
        alert(exception)
    }
};
// 打开通知
var onOpenNotification = function(event) {
    try {
        alert(JSON.stringify(event));
        var alertContent;
        if (device.platform == "Android") {
            alertContent = event.alert;
        } else {
            alertContent = event.aps.alert;
        }
        alert("open Notification:" + alertContent);
        if (event.extras.count == 3){
            alert("即将打开百度");
            location.href = "http://www.baidu.com"
        }
    } catch (exception) {
        alert("JPushPlugin:onOpenNotification" + exception);
    }
};
//获取通知内容
var onReceiveNotification = function(event) {
    try {
        var alertContent;
        if (device.platform == "Android") {
            alertContent = event.alert;
        } else {
            alertContent = event.aps.alert;
        }
        alert("把接受的通知显示在页面上");
        $("#notificationResult").html(alertContent);
    } catch (exception) {
        alert(exception)
    }
};
// 获取自定义消息推送内容
var onReceiveMessage = function(event) {
    try {
        var message;
        if (device.platform == "Android") {
            message = event.message;
        } else {
            message = event.content;
        }
        alert("把自定义的消息显示在页面上");
        $("#messageResult").html(message);
    } catch (exception) {
        alert("JPushPlugin:onReceiveMessage-->" + exception);
    }
};



summerready = function(){
	app.initialize();
}
```


<a target='_blank' style="font-size:20px" href="https://github.com/jpush/jpush-phonegap-plugin">用例github下载地</a>
