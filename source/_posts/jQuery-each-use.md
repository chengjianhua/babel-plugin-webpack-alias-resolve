---
title: jQuery $.each()用法解析
date: 2016-01-19 22:23:21
tags: [JavaScript, Note]
---

## jQuery $.each()用法解析


通过它，你可以遍历对象、数组的属性值并进行处理。

使用说明

each函数根据参数的类型实现的效果不完全一致：

1、 遍历对象(有附加参数)

```javascript
$.each(Object, function(p1, p2) {

     this;       //这里的this指向每次遍历中Object的当前属性值

     p1; p2;     //访问附加参数

}, ['参数1', '参数2']);
```

2、 遍历数组(有附件参数)

<!-- more -->

```javascript
$.each(Array, function(p1, p2){
     this;       //这里的this指向每次遍历中Array的当前元素
     
     p1; p2;     //访问附加参数

}, ['参数1', '参数2']);

```
 

3、 遍历对象(没有附加参数)
```javascript
$.each(Object, function(name, value) {

     this;      //this指向当前属性的值

     name;      //name表示Object当前属性的名称

     value;     //value表示Object当前属性的值

});
```
 

4、 遍历数组(没有附加参数)
```javascript
$.each(Array, function(i, value) {

     this;      //this指向当前元素

     i;         //i表示Array当前下标

     value;     //value表示Array当前元素

});
```
下面提一下jQuery的each方法的几种常用的用法

```javascript
 var arr = [ "one", "two", "three", "four"];     
 $.each(arr, function(){     
    alert(this);     
 });     
//上面这个each输出的结果分别为：one,two,three,four 
   
var arr1 = [[1, 4, 3], [4, 6, 6], [7, 20, 9]]     
$.each(arr1, function(i, item){     
   alert(item[0]);     
});     

//其实arr1为一个二维数组，item相当于取每一个一维数组，   
//item[0]相对于取每一个一维数组里的第一个值   
//所以上面这个each输出分别为：1   4   7     

var obj = { one:1, two:2, three:3, four:4};     
$.each(obj, function(key, val) {     
    alert(obj[key]);           
});   
//这个each就有更厉害了，能循环每一个属性     
//输出结果为：1   2  3  4
```