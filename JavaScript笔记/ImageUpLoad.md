# 图片上传

目前：  
选择图片 -> 上传图片  
1.input 输入框onChange时直接上传图片到后端，然后返回一串独一无二的数据（uuid）  
2.（可以发一个请求拿图片预览）（可选）   
3.由另外一个请求上传uuid和用户id来保存图片。   

新方法一：     
选择图片 -> 预览图片 -> 裁剪图片 -> 上传图片     
1.input输入框选择图片（type：file）可以选accept、capture属性    
2.使用 URL.createObjectURL 预览/使用 FileReader 预览    
3.关于图片的裁剪，可以使用 canvas 。但建议用图片裁剪库 cropperjs   
4.上传  


**URL.createObjectURL**   
···js
let url=window.URL.createObjectURL(e.target.files[0])
···
同步读取，返回的是URL 

** FileReader **   
```js
let a=new window.FileReader()
a.readAsDataURL(e.target.files[0])
a.onload=(e)=>{console.log(e)}//返回base64的图片
let imageUrl ='data:image/png;base64,' +btoa(new Uint8Array(imageData).reduce((data, byte) => data + String.fromCharCode(byte), ''));
```
FileReader（） 是一个构造函数
异步读取，返回的base64

