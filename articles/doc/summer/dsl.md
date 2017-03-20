## summer框架兼容方式

summer框架对DSL框架调用原生服务的方法做了兼容，原有的调用方式依然可以在summer框架中直接使用。具体做法是    
在html页面中引入summer.js 的同时，必须要先引入**iuapmobile.frameworks.core.js**，点击右键选择新建目录中的javaScript文件中的iuapmobile.frameworks.core.js。

**如图：**
![](/portal/upload/doc/20170209/20170209095244406.png)

**引入js：**

    <script src="js/Frameworks/iuapmobile.frameworks.core.js" ></script>    
    <script src="js/summer.js" ></script>    
    
#### 示例（1）兼容模式使用打开相机服务的示例代码：
         $camera.open({
		callback : function (sender, args){
			alert(typeof(args.imgPath)); //string
			alert(args.imgPath);
			$('.pic').attr('src',args.imgPath);
		  }
	  });
#### 示例（2）兼容模式使用生成二维码服务的示例代码：
        var twocodepath = $scanner.generateQRCode({
               size : 30,//二维码正方形的宽高
	       content : "text"//生成二维码所需的源文字 string类型
	 });
	var qq = twocodepath;		//string 图片路径 
	$('.pic').attr('src',qq);

### 兼容模式与标准模式API对比
#### 新版本的summer框架对调用原生服务的API做了调整，下表为全部API的调整，未列出项在新summer框架中不可用。
| 兼容模式  | 标准模式  |
| :------------: | :------------: |
| $device.getTimeZoneID | summer.getTimeZoneID  |
| $device.getTimeZoneDisplayName | summer.getTimeZoneDisplayName  |
| $device.getDeviceInfo | summer.getDeviceInfo  |
| $device.getLocation |   summer.getLocation|
| $device.capturePhoto |  summer.capturePhoto |
| $device.getAlbumPath | summer.getAlbumPath  |
| $device.getAppAlbumPath |  summer.getAppAlbumPath |
| $tel.saveContact |  summer.saveContact |
| $device.getContacts | summer.getContacts  |
| $device.openAddressBook |  summer.openAddressBook |
| $device.getInternalMemoryInfo |  summer.getInternalMemoryInfo |
| $device.getExternalStorageInfo | summer.getExternalStorageInfo  |
| $device.getMemoryInfo |  summer.getMemoryInfo |
| $device.openWebView |  summer.openWebView |
| $device.screenShot |  summer.screenShot |
| $device.notify |  summer.notify |
| $device.getScreenWidth |  summer.getScreenWidth |
| $device.getScreenHeight |  summer.getScreenHeight |
| $device.getScreenDensity |  summer.getScreenDensity |
| $device.currentOrientation | summer.currentOrientation  |
| $cache.write |  summer.writeFile |
| $cache.read |  summer.readFile |
| $camera.openPhotoAlbum |  summer.openPhotoAlbum |
| $camera.open |  summer.openCamera |
| $net.available | summer.netAvailable  |
| $net. getNetworkInfo |  summer. getNetworkInfo |
| $scanner.open | summer.openScanner  |
| $scanner.generateQRCode |  summer.generateQRCode |
| $service.get | summer.get  |
| $service.post | summer.post  |
| $service.callAction | summer.callAction  |
|$sqlite.openDB  |  summer.UMSqlite.openDB |
| $sqlite.execSql |  summer.UMSqlite.execSql |
| $sqlite.queryByPage |  summer.UMSqlite.queryByPage |
| $sqlite.exist |  summer.UMSqlite.exist |
| $sqlite.query |  summer.UMSqlite.query |
| $tel.call | summer.callPhone  |
| $tel.sendMsg | summer.sendMsg  |
| $tel.sendMail |  summer.sendMail |
| $file.remove |  summer.removeFile |
| $file.exists |  summer.exists |
| $file.download |  summer.download |
| $file.open |   summer.openFile|
|$file.getFileInfo  |  summer.getFileInfo|
|$file.getFileInfo  |  summer.getFileInfo|












