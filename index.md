# Javascript编码规范
>写在前面：本文适用于前端团队协作时使用，目的为形成统一的编码风格，仅供参考。这里也先简单介绍下几种常见的命名法：匈牙利命名法，编写规范为“变量名=[属性＋]类型＋对象描述”，这种写法可以看出变量的一些基础信息，如：m_strName；骆驼式命名法，主要采用大小写混合的方式来表示变量，这种方式目前较为流行，如：myName(小驼峰)；帕斯卡命名法（也可叫大驼峰命名法），变量名以几个大写字母开头的单词拼接而成，如：MyName；下划线命名法：采用下划线来拆分单词，如：my_name，在C语言中较为常见。

# 一、命名规范

## 1、变量名

变量名包括全局变量、局部变量、函数的传参等，采用比较直观的“小驼峰命名法”（即：首字母小写）来编写，如：

```javascript
let myName = "Johnxy"
```

## 2、常量名

采用全大写的下划线命名方式，如：
```javascript
const BASIC_CONFIG = {}
```

## 3、函数名

函数名和变量名类似，采用比较直观的“小驼峰命名法”来编写，如：
```javascript
function sayHi() {
  console.log("Hi!Johnxy.");
}

sayHi()
```

## 4、构造函数及类名

采用帕斯卡命名法，这样可以与普通函数做一些区分，如：
```javascript
class User {
  constructor(name) {
    this.name = name;
    return this;
  }
  
  sayHi() {
    console.log("Hi!" + this.name + ".");
  }
}

new User("Johnxy").sayHi()
```


# 二、注释规范

## 1、常规注释

- 单行注释，采用“//”的注释方式，用一个空格和内容隔开，如：
```javascript
// 用来记录用户个数
let userTotalNum = 0
```
- 多行注释，采用“/*注释内容*/”的方式，注释内容前用一个空格隔开，如：
```javascript
/**
 * 显示我的名字
 * @param string name 缺省值为johnxy
 */
function showName(name = "johnxy") {
  console.log("Hi!" + name);
}
```

## 2、函数必要的注释说明

一个函数的必要说明可以帮助不同的代码维护人员快速了解函数作用，从而提高团队效率。另外，符合规范的编写，可以快速生成API供其他开发人员查阅，方便复用代码。
```javascript

/**
 * 设置用户信息
 * @param object info 用户基本信息
 * @param string info.name  用户姓名
 * @param number info.age   用户年龄
 * @description 备注一些注意事项
 * @example
 *   setUserInfo({name : "Johnxy", age : 18})
 */
function setUserInfo(object) {
  this.name = object.name
  this.age = object.age
}
```

