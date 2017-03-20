## 摄像图库

### 调用方法
```javascript
var pictureSource;   // picture source   
var destinationType; // sets the format of returned value  
document.addEventListener("deviceready",onDeviceReady,false);  
function onDeviceReady() {
	pictureSource=navigator.camera.PictureSourceType;        
	destinationType=navigator.camera.DestinationType;    
}     
function onPhotoDataSuccess(imageData) {        
       
	var smallImage = document.getElementById('smallImage');        
	smallImage.style.display = 'block';        
	smallImage.src = "data:image/jpeg;base64," + imageData; 
} 
// Called when a photo is successfully retrieved    //     
function onPhotoURISuccess(imageURI) {        
    
	var largeImage = document.getElementById('largeImage');        
	largeImage.style.display = 'block';        
	largeImage.src = imageURI;    
}      
// A button will call this function    //      
function capturePhoto() {      
	//navigator.camera.getPicture(onPhotoDataSuccess, onFail, { quality: 50,destinationType: destinationType.DATA_URL }); 
	navigator.camera.getPicture(onPhotoDataSuccess,onFail, { quality: 50,destinationType: destinationType.DATA_URL })
}      
// A button will call this function    //     
function capturePhotoEdit() {       
	//navigator.camera.getPicture(onPhotoDataSuccess, onFail, { quality: 20, allowEdit: true,        destinationType: destinationType.DATA_URL });    
	navigator.camera.getPicture(onPhotoDataSuccess,onFail,{ quality: 20, allowEdit: true,destinationType: destinationType.DATA_URL })
}      
// A button will call this function    //      
function getPhoto(source) {        
	//navigator.camera.getPicture(onPhotoURISuccess, onFail, { quality: 50,        destinationType: destinationType.FILE_URI,        sourceType: source });
	navigator.camera.getPicture(onPhotoURISuccess,onFail,{ quality: 20, destinationType: destinationType.FILE_URI,sourceType: source })
}      
// Called if something bad happens.    //     
function onFail(message) {      
	alert('Failed because: ' + message);    
}     

```

<a target='_blank' style="font-size:20px" href="https://github.com/iuapmobile/summerTest/tree/master/cordovaTest/xcamera">用例github下载地</a>

<a target='_blank' style="font-size:20px" href="https://www.npmjs.com/package/cordova-plugin-camera">更多参见</a>
