## 打开studio在左侧列表中找到config.xml文件，双击打开，选择插件选项勾选cordova-plugin-contacts文件，并在权限选项中选择相关权限。最后保存文件。
## 联系人
###summer框架中的联系可以使用cordova插件(cordova-plugin-contacts)，主要功能包含：    
####1、查寻联系人                   
    navigator.contacts.find({    
        'filter':'xxx',  //查询联系人的字段选项   
        'multiple':true,  //是否返回多个查询结果 
        'hasPhoneNumber':true,  //是否只返回联系电话号码  
        'desiredFields':[navigator.contacts.fieldType.name],  //返回联系人的对象包含的字段的值（可以选择不同的返回值）    
        'fieldType':[navigator.contacts.fieldType.name]},  //按照该字段选项查询联系人（可以多选）   
         function (contacts) {    
             alert(contacts);  //成功返回的数据
             alert(navigator.contacts.fieldType);  //所有字段选项  
         },    
         function (contactError) {    
            alert('onError!');   //失败返回的错误信息
         }    
    )  
####2、保存联系人
```javascript
function onSuccess(contact) {
		alert("Save Success");
	};

	function onError(contactError) {
		alert("Error = " + contactError.code);
	};

// create a new contact object
	var contact = navigator.contacts.create();
	contact.displayName = "海滨2";
	contact.nickname = "qq2";            // specify both to support all devices
// save to device
	contact.save(onSuccess,onError);
```


<a target='_blank' style="font-size:20px" href="https://github.com/iuapmobile/summerTest/tree/master/cordovaTest/qContacts">用例github下载地</a>

<a target='_blank' style="font-size:20px" href="https://www.npmjs.com/package/cordova-plugin-contacts">更多参见</a>
