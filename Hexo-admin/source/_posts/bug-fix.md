---
title: bug-fix
date: 2017-09-19 15:56:36
tags:
---

####  bug-fix
 总结一下遇到的问题 , 希望有所改进

1. timerHelper 
   账户级数据统计上线后,9月10号遇到了一个线上bug,初始化时,请求数据要传递两个参数(开始时间start,结束时间end),
   显示传递的参数值为(start:'2017-09-08' end:'017-08-010'),传递的时间不合法,导致请求接口报错,页面无法
   加载,最后定位到原因:
   因为页面加载时候默认请求最近30天的时间,timeForMat方式实现这个功能时是有问题的
   
   方法实现方式为:
   
   ```
   export function timeForMat(count) {
       // 拼接时间
       let time1 = new Date()
       time1.setTime(time1.getTime() - (24 * 60 * 60 * 1000))
       let Y1 = time1.getFullYear()
       let M1 = ((time1.getMonth() + 1) > 10 ? (time1.getMonth() + 1) : '0' + (time1.getMonth() + 1))
       let D1 = (time1.getDate() > 10 ? time1.getDate() : '0' + time1.getDate())
       let timer1 = Y1 + '-' + M1 + '-' + D1 // 当前时间
       let time2 = new Date()
       time2.setTime(time2.getTime() - (24 * 60 * 60 * 1000 * count))
       let Y2 = time2.getFullYear()
       let M2 = ((time2.getMonth() + 1) > 10 ? (time2.getMonth() + 1) : '0' + (time2.getMonth() + 1))
       let D2 = (time2.getDate() > 10 ? time2.getDate() : '0' + time2.getDate())
       let timer2 = Y2 + '-' + M2 + '-' + D2 // 之前的7天或者30天
       return {
           t1: timer1,
           t2: timer2
       }
   }
   ```
   问题出在当计算M1和M2的时候的写法
   ```
   ((time2.getMonth() + 1) > 10 ? (time2.getMonth() + 1) : '0' + (time2.getMonth() + 1))
   ```
   忘记了处理等于10的情况,导致等于10的时候,前边也拼接了0,最后的处理方法有两个:
   1. 
   ```
   ((time2.getMonth() + 1) > 10 ? (time2.getMonth() + 1) : '0' + (time2.getMonth() + 1))
   ```
   2.
   ```
   timer1 = Y1 + '-' + M1 + '-' + parseInt(D1)
   timer2 = Y2 + '-' + M2 + '-' + parseInt(D2)
   ```
   
   这个问题要注意测试的时候对边界值的测试