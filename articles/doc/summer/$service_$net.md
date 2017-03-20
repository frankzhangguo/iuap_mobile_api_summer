# $net
是获取当前设备网络信息的服务对象

## $net.available()
该方法用来获取网络是否可用的状态，返回值为为boolean类型true||false

**示例代码**
```javascript
var net=$net.available()
```

## $net. getNetworkInfo()
该方法用来获取当前网络信息，返回当前设备网络信息，返回值为json类型{"Type":"WiFi"}

**示例代码**
```javascript
var net =$net. getNetworkInfo()
```

<a target='_blank' style="font-size:20px" href="https://github.com/iuapmobile/summerTest/tree/master/xServiceTest/qNet">用例github下载地</a>
