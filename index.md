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
  console.log("Hi!Johnxy.")
}

sayHi()
```

## 4、构造函数及类名

采用帕斯卡命名法，这样可以与普通函数做一些区分，如：
```javascript
class User {
  constructor(name) {
    this.name = name
    return this
  }
  
  sayHi() {
    console.log("Hi!" + this.name + ".")
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
  console.log("Hi!" + name)
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
# 三、代码书写规范

## 1、空格约定

- 默认缩进方案采用“两个空格”方案，这是业界大部分团队采用的方式，所以请在IDE里设置好，以方便做自动格式化，当然你也可以用一些自动化的方式来处理，如：安装一些现成的插件。
- 函数方法定义的花括号前添加一个空格
- 多个参数传递分隔的逗号后添加一个空格
- 对象用冒号前后各添加一个空格

常见示例代码如下：

```javascript
/**
 * 设置用户信息
 * @param object info 用户基本信息
 * @param string info.name  用户姓名
 * @param number info.age   用户年龄
 * @callback function cb    初始化完成的回调方法
 * @description 备注一些注意事项
 * @example
 *   setUserInfo({name : "Johnxy", age : 18})
 */
 function setUserInfo(object, cb) {
  this.name = object.name
  this.age = object.age
  cb && cb(this)
}

setUserInfo({name : "Johnxy", age : 18})
 ```
## 2、换行约定

为让你的代码好看，请设置80个字符后自动换行，这样方便阅读，在大部分场景下是不会出现这种超长的链式调用的，如果有请在每个调用前做换行处理。如：
```javascript

// 不好的示例：这段注释非常长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长

/** 好的示例：这段注释非常长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长
 *  长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长
 */

// 不好的示例
functionA().functionB().functionC().functionD().functionE().functionF()

// 好的示例
functionA()
  .functionB()
    .functionC()
      .functionD()
        .functionE()
          .functionF()
          
```


