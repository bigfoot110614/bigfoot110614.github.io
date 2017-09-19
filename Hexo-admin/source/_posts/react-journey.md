---
title: react journey
date: 2017-07-06 18:28:57
tags:
---

#### 学习react项目需要学习的东西
参考资料: 阮一峰 ECMAScript 6 入门
着重熟悉内容：变量解构语法、字符串扩展、函数扩展（箭头函数：箭头函数中的this）、promise、class、Module语法
使用解构语法来设置默认值（react组件从props中获取变量）和复制新对象（reducer处理）
可以使用装饰器语法
编码规范

参考资料 ESLint使用入门 /ESLint官网 /Airbnb React /Airbnb js风格指南
eslint配置路径 /internal_training/assets/.eslintrc，使用Airbnb的开发风格，但是部分做了改动：禁止使用分号、react*函数组件可以允许箭头函数*，可以查看eslintrc中放开了哪些规则。
各位猿可以在自己熟悉的IED中配置指定eslint使用上述路径作为ESLint的配置文件 
如果是VScode可以在setting的工作区设置中加入以下配置，指定eslintrc和eslintignore文件生效的位置
"eslint.options": {
     "cwd": "/Users/Jackson/mudu/code/internal_training/assets"
},
如果出现ESLint 信息，大家尽量按照提示进行修改，不用追求100%达到ESLint的要求，部分规则会在eslintrc中放开
现在实行的是较为宽松的编码规范，到达美观，符合通用规范即可，希望大家养成良好的代码规范
#### 1.git
#### 2.ES6
#### 1.git
#### 1.git
#### 1.git





git

参考资料: 廖雪峰git教程 git工作流程
有课大致按照git flow流程来处理分支，只是去除了develop分支
React

参考资料: React官网入门手册 /阮一峰React入门 有课代码可以从/internal_training/assets/src/modules/audience/entry.js入手，查看用React如何写观众登录页
Antd

组件地址：Antd 和 Antd Mobile
蚂蚁金服开发的react组件，方便与设计人员统一UI样式，同时提高前端开发的效率
Antd的样式代码路径：/internal_training/assets/global_modules/antd@2.1.0，可以直接定制自己的样式文件
手机端
Redux 和React-Redux

参考资料 阮一峰Redux入门教材 /Redux中文文档 /React-Redux /react组件设计和分解思考
console和watch页面使用了redux和react-redux
使用redux-thunk处理异步操作中间件与异步操作和异步Dispatch，/internal_training/assets/src/modules/console/ajaxOperations下的都是此类异步操作
redux中的store处理参考了极牛redeux性能优化实践和state范式化，store分为entities（数据库数据）和view（UI共享数据）两部分，/internal_training/assets/src/modules/console/entities定义了控制台页面的entities部分reducer
React-Router（v4）

参考资料 React-router
console页面是一个单页面应用，使用了react-router，文件地址/internal_training/assets/src/modules/console/routes
/linternal_training/assets/src/modules/console/views/live-studio/components/LiveStudio.jsx使用了子路由
Webpack

参考资料 目睹直播webpack资料（注意有课的hot-dev端口是8081， 使用热更新需要将本机的8081映射到docker内）
使用yarn代替npm下载node 包
查看package.json的script，熟悉编译命令对应的具体指令，可以看到每条命令使用的webpack文件，主要是internal_training/assets/build/webpack.all.config.js
使用postcss的autoprefix对css代码进行了兼容补全
手机端使用pxtorem对px单位进行了转换，使用rem以到达自适应，antd-mobile高清方案
 