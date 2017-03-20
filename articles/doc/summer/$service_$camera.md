**目录**

[TOC]

# $camera
是对相机、图库等操作的服务对象

## $camera.open()
该方法用来打开系统相机，支持回调callback。通常获取相机拍摄的照片通过callback来实现。

**代码演示**
```javascript
$camera.open({
	callback : function(args){
		$('.pic').attr('src',args.imgPath)
		//返回的args是个json对象，key值为imgPath是照片的路径类型为string
	}
})
```

## $camera.openPhotoAlbum()
该方法用来打开系统相册

**代码演示**
```javascript
$camera.openPhotoAlbum({
	callback : function (arges){
		$('.pic').attr('src',args.imgPath)
		//返回的args是个json对象，key值为imgPath是照片的路径类型为string
	}
})
```

<a target='_blank' style="font-size:20px" href="https://github.com/iuapmobile/summerTest/tree/master/xServiceTest/qCamera">用例github下载地</a>
