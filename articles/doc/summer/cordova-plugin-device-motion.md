## 加速计

####1、获取加速计                  
    function getMotion(){
        navigator.accelerometer.getCurrentAcceleration(onSuccess);
    };
####2、传参来获取加速计 
    function watchMotion(){
        var options = { frequency: 1000 };  // Update every 1 seconds
        navigator.accelerometer.watchAcceleration(options,onSuccess);
    }
### 成功回调
    function onSuccess(acceleration) {
        alert('Acceleration X: ' + acceleration.x + '\n' +
            'Acceleration Y: ' + acceleration.y + '\n' +
            'Acceleration Z: ' + acceleration.z + '\n' +
            'Timestamp: '      + acceleration.timestamp + '\n');
    }
### 失败回调
    function onError() {
        alert('onError!');
    }


<a target='_blank' style="font-size:20px" href="https://github.com/iuapmobile/summerTest/tree/master/cordovaTest/xMotion">用例github下载地</a>

<a target='_blank' style="font-size:20px" href="https://www.npmjs.com/package/cordova-plugin-device-motion">更多参见</a>