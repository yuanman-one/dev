# json的转换

[TOC]

## json

### json简介

- json是一种存储数据的方式，轻量级的文本数据交换格式
     注意：轻量级相对于xml，json解析速度更快，文档更小

### 语法

1. 使用json表示一个对象
    {"属性名称"：属性值,"属性名称"：属相值,....}
    注意：属性名称必须用双引号引起来
    属性值可以为数字，字符串（用双引号引起来），布尔值，数组，对象，null

2. 将多个json对象装进一个数组
  [{"属性名称"：属性值,"属性名称"：属相值,....}]
  注意：json字符串使用双引号引起来的，不能通过变量名称.属性名称获取属性值
  但是json对象可以通过变量名称.属性名称，获取属性值

### 数据格式转换

- json字符串转换成json对象
  1. 使用js语言原生的函数`eval("(执行的内容)")`
   注意：针对有些容器不兼容，如IE6，IE7，兼容IE8
  2. 使用原生JSON对象提供的parse()方法
   `JSON.parse()`
   注意：JSON如果无效，说明浏览器版本太低了
  3. 使用jq提供的parse.JSON
   `$.parse.JSON(json字符串)`
   可以兼容各个浏览器
- 将json对象转换成json字符串
  1. 通过`JSON.stringify(json对象)`
- 将json字符串转换成java对象
  1. 导入fastjson-1.2.9.jar
  2. 转换java基本对象
   `JSON.parseObject(json字符串，类名.class)`
  3. 转换成数组
   `JSON.parseArray(json字符串)`
  4. 转换成list集合
   `JSON.parseArray(json字符串，类名.class)`
  5. 转换成map集合
   `JSON.parseObject(json字符串)`
- java对象转成json字符串
  1. 基本对象，数组，list集合，map集合转json字符串
   `JSON.toJsonString(对象名称)`
