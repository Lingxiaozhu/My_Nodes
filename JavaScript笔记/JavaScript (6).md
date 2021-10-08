JavaScript 表单
====
HTML 表单的内容能够通过 JavaScript 验证  
    例子：  

```js  
    function validateForm() {
    var x = document.forms["myForm"].value;
    if (x == "") {
        alert("必须填写姓名");
        return false;
        }
    }
```

JavaScript 验证 API   

    约束验证 DOM 方法:  
    checkValidity()  
    setCustomValidity()  




