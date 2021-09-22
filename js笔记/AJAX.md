AJAX 简介
===

AJAX可以不刷新页面更新网页，在页面加载后从服务器请求数据、接受数据，在后台向服务器发送数据  
AJAX =Asynchronous JavaScript And Xml  
AJAX并非编程语言  
AJAX仅仅结合了浏览器内建的XMLHttpRequest对象，Javascript和HTML DOM  
AJAX可以用XML、纯文本或JSON格式传输数据  
AJAX 允许通过与场景后面的 Web 服务器交换数据来异步更新网页。这意味着可以更新网页的部分，而不需要重新加载整个页面  
AJAX工作流程：
1. 事件（页面加载、按钮点击）  
2. 由JavaScript创建XMLHttpRequest对象  
3. XMLHttpRequest对象向web服务器发送请求  
4. 服务器处理请求  
5. 服务器将响应发送回网页  
6. 由JavaScript读取响应  
7. 由JavaScript执行正确的动作

AJAX - XMLHttpRequest 对象
===
AJAX的核心是XMLHttpRequest对象   
创建XMLHttpRequest语法：  
```js 
let a;
a=new XMLHttpRequest();
```

由于安全原因，现代浏览器不允许跨域访问，意味着加载的网页和XML文件都必须位于相同的服务器  

**XMLHttpRequest对象方法：**  
|方法|描述|  
|---|---|  
|new XMLHttpRequest()|创建新的XMLHttpRequest对象|  
|abort()|取消当前请求|  
|getAllResponseHeaders()|返回头部信息|  
|getResponseHeader()|返回特定的头部信息|  
|open(method, url, async, user, psw)|method：请求类型 GET 或 POST  url：文件位置  async：true（异步）或 false（同步）  user：可选的用户名称  psw：可选的密码|  
|send()|将请求发送到服务器，用于 GET 请求|  
|send(string)|将请求发送到服务器，用于 POST 请求|  
|setRequestHeader()|向要发送的报头添加标签/值对|   


**XMLHttpReques对象属性：**  

属性|描述|   
|---|---|  
|onreadystatechange|定义当 readyState 属性发生变化时被调用的函数|   
|readyState|保存 XMLHttpRequest 的状态|   
|responseText|以字符串返回响应数据|  
|responseXML|以 XML 数据返回响应数据|   
|status|返回请求的状态号|   
|statusText|返回状态文本（比如 "OK" 或 "Not Found"）| 



AJAX - 向服务器发送请求
===
XMLHttpRequest对象用于同服务器交换数据  
open() 方法的 url 参数，是服务器上文件的地址  

AJAX - 服务器响应
===
readyState 属性存留 XMLHttpRequest 的状态  
onreadystatechange 属性定义当 readyState 发生变化时执行的函数  
status 属性和 statusText 属性存有 XMLHttpRequest 对象的状态  
