## 打开studio在左侧列表中找到config.xml文件，双击打开，选择插件选项勾选cordova-plugin-barcodescanner文件，并在权限选项中选择相关权限。最后保存文件。
## 条码扫描器
###summer框架中的联系可以使用cordova插件(cordova-plugin-barcodescanner)，主要功能包含：    
####1、扫描二维码                   
    cordova.plugins.barcodeScanner.scan(
       function (result) {
          alert("We got a barcode\n" +
                "Result: " + result.text + "\n" +  //数据文本
                "Format: " + result.format + "\n" + //类型
                "Cancelled: " + result.cancelled); //是否取消扫描
       }, 
       function (error) {
          alert("Scanning failed: " + error);
       }
    );

####2、生成二维码                   
```javascript  
cordova.plugins.barcodeScanner.encode(
   	   BarcodeScanner.Encode.TEXT_TYPE, //类型
   	   "http://www.baidu.com",   //数据文本
   	   function(success) {
                alert("encode success: " + success); //成功会掉
           }, function(fail) {
                alert("encoding failed: " + fail);  //错误回调
           }
    );
```

<a  target='_blank' style="font-size:20px" href="https://github.com/iuapmobile/summerTest/tree/master/cordovaTest/qBarcodescanner">用例github下载地</a>



<a target='_blank' style="font-size:20px" href="https://www.npmjs.com/package/cordova-plugin-barcodescanner">更多参见</a>
