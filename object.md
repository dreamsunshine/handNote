# Object.defineProperty\(object,property,descriptor\)  //descriptor:{configurable,enumberable,writable,value} //ie8以上

## 数据属性：

1、\[Configurable\]: //false表示不能从对象中删除属性，设置后不可变更

2、\[Enumerable\]

3、\[Writable\]

4、\[Value\]

## 访问器属性

1、 \[Configurable\]  //能否通过delete删除  
2、 \[Enumerable\]  //能否通过for-in循环返回属性  
3、 \[Get\]  
4、 \[Set\]  
//旧浏览器创建访问器属性\_\_defineGetter\_\_和\_\_defineSetter\_\_

# Object.getOwnpropertyDescriptor\(object,property\)  //IE9+

# 创建对象

## 1、工厂模式 //解决创建多个相似对象，未解决对象识别问题

```
function createPerson(name,age){
   var o=new Object();
    o.name=name;
    o.age=age;
    //函数实现
    return o;
}
```

## 2、构造函数模式

```
function Person(name,age){
    this.name=name;
    this.age=age;
    this.sayName=function(){};
}
```

//通过new操作符创建实例，实例均有constructor\(构造函数\)属性

## 3、原型模式

//创建的函数均有prototype\(原型\)属性，prototype就是通过调用构造函数而创建的那个对象实例的原型对象。实例共享属性和方法。

```
function Person(){}
Person.prototype.name="some";
Person.prototype.age="some";
Person.prototype.sayName=function(){};
```

/理解原型对象：新函数自动获得prototype属性，指向函数的原型对象。所有原型对象自动获得constructor属性，这个属性包含一个指向prototype属性所在函数的指针。

//自定义的构造函数只会取得constructor属性，其他从Object继承而来。

//isPrototypeOf  判断实例归属关系

//Object.getPrototypeOf\(object\) 取得object对象的原型IE9+

//hasOwnProperty\(\) 在对象实例中返回true

//for in列举属性，Object.keys\(\)所有可枚举属性,Object.getOwnPropertyNames\(\)列举所有实例属性，后两者IE9+

## 4、原型链

```
function SuperType(){
    this.property=true;
}
function SubType(){
    this.property=false;
}
SubType.prototype=new SuperType();
```

//实质是重写原型对象。

## 5、借用构造函数

```
function SuperType(){
    //定义属性
}
function SubType(){
    SuperType.call(this,'')//传递参数
}
```



