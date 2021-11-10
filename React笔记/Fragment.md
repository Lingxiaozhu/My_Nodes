# React.Fragments
Fragments 可以让你聚合一个子元素列表，并且不在DOM中增加额外节点。  

Fragments 看起来像空的 JSX 标签：  
```js
rander(){
return(
<>
...
</>
);
}
```
注意在 React 中， <></> 是 <React.Fragment/> 的语法糖  
<></> 语法不能接受键值或属性。  
需要一个带 key 的片段，你可以直接使用 <React.Fragment /> 。  

**语法糖(syntactic sugar)是指编程语言中可以更容易的表达一个操作的语法**