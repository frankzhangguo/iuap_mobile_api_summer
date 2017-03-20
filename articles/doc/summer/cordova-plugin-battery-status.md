## 电池信息

####1、电池电量变化信息                   
```javascript
window.addEventListener("batterystatus", onBatteryStatus, false);
function onBatteryStatus(status) {
        $summer.alert(status);
        alert("Level: " + status.level + " isPlugged: " + status.isPlugged);
    }
```

<a target='_blank' style="font-size:20px" href="https://github.com/iuapmobile/summerTest/tree/master/cordovaTest/xBatteryStatus">用例github下载地</a>

<a target='_blank' style="font-size:20px" href="https://www.npmjs.com/package/cordova-plugin-battery-status">更多参见</a>