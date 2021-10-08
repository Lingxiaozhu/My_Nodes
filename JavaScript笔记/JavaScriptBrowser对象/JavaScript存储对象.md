JavaScript 存储对象  
===

Web存储API提供了sessionStorage（会话存储）和localStorage（本地存储）两个存储对象来对网页的数据进行添加、删除、修改、查询操作  

Web 存储 API
---

|API|描述|  
|---|----|  
|window.localStorage|浏览器中存储 key/value 对，没有过期时间|  
|window.sessionStorage|浏览器中存储 key/value 对，关闭窗口或标签页后会删除这些数据|  
 
语法例子
---
|API|语法例子|  
|---|----|  
|window.localStorage|localStorage.setItem("key", "value")|  
|window.sessionStorage|sessionStorage.setItem("key", "value");|  

存储对象方法  
---

|方法|描述|  
|---|---|  
|key(n)|返回存储对象中第 n 个键的名称|  
|getItem(keyname)|返回指定键的值|  
|setItem(keyname, value)|添加键和值，如果对应的值存在，则更新该键对应的值|  
|removeItem(keyname)|移除键|  
|clear()|清除存储对象中所有的键|  

存储对象属性
---

|属性|方法|  
|---|---|  
|length|返回存储对象中包含多少条数据|  


localStorage 和 sessionStorage区别
---

* localStorage 和 sessionStorage 属性允许在浏览器中存储 key/value 对的数据  
* localStorage 用于长久保存整个网站的数据，保存的数据没有过期时间，直到手动去删除  
* localStorage 属性是只读的  
* 如果只想将数据保存在当前会话中，使用 sessionStorage 属性，该数据对象临时保存同一窗口(或标签页)的数据，关闭窗口或标签页后将会删除这些数据