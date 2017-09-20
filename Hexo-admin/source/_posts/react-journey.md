---
title: react journey
date: 2017-07-06 18:28:57
tags:
---
今年七月三号开始接触react,由于工作需要,要不断的了解和应用react全家桶,git和es6也是必不可少,接下来记录一下在工作中遇到的一些问题

1.export 和 export default
 与其说说这是react中的知识点,不如说这是es6中的知识点,现在就来比较一下es5和es6的区别
 
  - es6导入用import...from 代替了 require
  - es6导出用export 替换了 module.exports
  - 现在对比export和 export default 的区别, export default 只能导出一个,但是export可以导出多个,
   如果一个模块是用export导出的,那么就只能用下边方式引入
   
   ```
    import {模块} from ''
   ```
   如果一个模块是用export default 导出的,那么久只能用下边的方式引入
   ```
   import 模块 from ''
   ```
   
2.antd tabs 样式问题

3.git diff 算法

4.unit test 方法问题

5.webpack使用问题

6.mac和linux 文件名大小写的问题

7.关于react 下 使用echart的方法和感想

8.git的一些用法 在此项目上踩到的坑

9.
   
   
   