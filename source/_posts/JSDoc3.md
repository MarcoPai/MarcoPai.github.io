title: JSDoc3
tags:
  - javascript
  - nodejs
  - jsdoc
  
categories:
  - tools
  
date: 2014-07-17 17:38:35
updated: 2014-07-17 17:38:35
---

### 相关站点：

官方网站：https://github.com/jsdoc3/jsdoc/
书写规范：http://usejsdoc.org/
相关介绍：http://blog.csdn.net/wts/article/category/1226952

中文说明：http://clientlab.github.io/lessons/2013/10/24/build-api-document-by-jsdoc3/
实战说明：[使用jsdoc生成组件API文档—jsdoc实战](http://www.36ria.com/5101)


### JSDoc支持的命令属性：

命令名           |              描述 
----------------|-------------
@param          |
@argument       |  指定参数名和说明来描述一个函数参数。 
@return         |
@returns        |  描述函数的返回值。 
@author         |  指示代码的作者。 
@deprecated     |  指示一个函数已经废弃，不建议使用，而且在将来版本的代码中可能会彻底删除。要避免使用这段代码。 
@see            |  创建一个HTML链接指向指定类的描述。 
@version        |  指定发布版本。 
@requires       |  创建一个HTML链接，指向这个类所需的指定类。 
@throws         |
@exception      |  描述函数可能抛出的异常的类型。 
{@link}         |  创建一个HTML链接，指向指定的类。这与@see很类似，但{@link}能嵌在注释文本中。 
@author         |  指示代码的作者。（译者注：这个标记前面已经出现过，建议去掉） 
@fileoverview   |  这是一个特殊的标记，如果在文件的第一个文档块中使用这个标记，则指定该文档块的余下部分将用来提供文件的一个概述。 
@class          |  提供类的有关信息，用在构造函数的文档中。 
@constructor    |  明确一个函数是某个类的构造函数。 
@type           |  指定函数的返回类型。 
@extends        |  指示一个类派生了另一个类。通常JSDoc自己就可以检测出这种信息，不过，在某些情况下则必须使用这个标记。 
@private        |  指示一个类或函数是私有的。私有类和函数不会出现在HTML文档中，除非运行JSDoc时提供了—private命令行选项。
@final          |  指示一个值是常量值。要记住JavaScript无法真正保证一个值是常量。 
@ignore         |  JSDoc会忽略有这个标记的函数。

<!--more-->

### Tag Dictionary

name                                        |           describe
--------------------------------------------|-------------------------------------------
@abstract (synonyms: @virtual)              |   This member must be implemented (or overridden) by the inheritor.
@access                                     |   Specify the access level of this member (private, public, or protected).
@alias                                      |   Treat a member as if it had a different name.
@augments (synonyms: @extends)              |   This object adds onto a parent object.
@author                                     |   Identify the author of an item.
@borrows                                    |   This object uses something from another object.
@callback                                   |   Document a callback function.
@class (synonyms: @constructor)             |   This function is intended to be called with the "new" keyword.
@classdesc                                  |   Use the following text to describe the entire class.
@constant (synonyms: @const)                |   Document an object as a constant.
@constructs                                 |   This function member will be the constructor for the previous class.
@copyright                                  |   Document some copyright information.
@default (synonyms: @defaultvalue)          |   Document the default value.
@deprecated                                 |   Document that this is no longer the preferred way.
@description (synonyms: @desc)              |   Describe a symbol.
@enum                                       |   Document a collection of related properties.
@event                                      |   Document an event.
@example                                    |   Provide an example of how to use a documented item.
@exports                                    |   Identify the member that is exported by a JavaScript module.
@external (synonyms: @host)                 |   Document an external class/namespace/module.
@file (synonyms: @fileoverview, @overview)  |   Describe a file.
@fires (synonyms: @emits)                   |   Describe the events this method may fire.
@function (synonyms: @func, @method)        |   Describe a function or method.
@global                                     |   Document a global object.
@ignore                                     |   [todo] Remove this from the final output.
@inner                                      |   Document an inner object.
@instance                                   |   Document an instance member.
@kind                                       |   What kind of symbol is this?
@lends                                      |   Document properties on an object literal as if they belonged to a symbol with a given name.
@license                                    |   [todo] Document the software license that applies to this code.
@link                                       |   Inline tag - create a link.
@member (synonyms: @var)                    |   Document a member.
@memberof                                   |   This symbol belongs to a parent symbol.
@mixes                                      |   This object mixes in all the members from another object.
@mixin                                      |   Document a mixin object.
@module                                     |   Document a JavaScript module.
@name                                       |   Document the name of an object.
@namespace                                  |   Document a namespace object.
@param (synonyms: @arg, @argument)          |   Document the parameter to a function.
@private                                    |   This symbol is meant to be private.
@property (synonyms: @prop)                 |   Document a property of an object.
@protected                                  |   This member is meant to be protected.
@public                                     |   This symbol is meant to be public.
@readonly                                   |   This symbol is meant to be read-only.
@requires                                   |   This file requires a JavaScript module.
@returns (synonyms: @return)                |   Document the return value of a function.
@see                                        |   Refer to some other documentation for more information.
@since                                      |   When was this feature added?
@static                                     |   Document a static member.
@summary                                    |   A shorter version of the full description.
@this                                       |   What does the 'this' keyword refer to here?
@throws (synonyms: @exception)              |   Describe what errors could be thrown.
@todo                                       |   Document tasks to be completed.
@tutorial                                   |   Insert a link to an included tutorial file.
@type                                       |   Document the type of an object.
@typedef                                    |   Document a custom type.
@variation                                  |   Distinguish different objects with the same name.
@version                                    |   Documents the version number of an item.



### Example

名称             | 描述
----------------|-------------
@author:        | 作者
@argument:      | 参数
@augments:      | 参数
@class          | 类
@constant       | 常数
@constructor    | 构造
@constructs     | 构造
@default        | 默认值
@deprecated     | 推荐，说明使用一个变量已不再支持
@description    | 说明
@example        | 范例
@extends        | 扩展 ，继承
@field          | 变量（非功能）
@fileOverview   | 整个文件信息
@function       | 功能 (表示该变量指向一个功能)
@inner          | 内部
@private        | 私有
@ignore         | 忽视 （文档生成的式后也将忽视这个变量）
@event          | 事件
@version        | 版本
@type           | 类型 描述预期的类型变量的值或返回值的函数
@throws         | 可能抛出的异常
@static         | 静态，访问该变量不需要实例
@since          | 自 （表明某属性特征，是在什么版本之后才有的）
@see            | 描述相关的资源
@scope          | 作用域
@lends          | 作用域
@return         | 返回值
@returns        | 返回值
@requires       | 描述必须需要的资源
@public         | 说明内在变量是公开的
@property       | 属性
@param          | 参数
@namespace      | 命名空间