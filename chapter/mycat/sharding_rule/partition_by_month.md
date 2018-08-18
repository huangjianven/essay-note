# 自然月 partitionByMonth
可设置属性：
* dateFormat  ： 日期格式化，默认为 yyyy-MM-dd
* sBeginDate  ： 开始日期，无默认值
* sEndDate   ：结束日期，无默认值

> 节点从0开始

## 场景1
默认设置；节点数量必须是12个，从1月~12月
* "2014-01-01" = 节点0
* "2013-01-01" = 节点0
* "2018-05-01" = 节点4
* "2019-12-01" = 节点11

## 场景2
sBeginDate = "2017-01-01"

该配置表示"2017-01月"是第0个节点，从该时间按月递增，无最大节点

*  "2014-01-01" = 未找到节点
*  "2017-01-01" = 节点0
*  "2017-12-01" = 节点11
*  "2018-01-01" = 节点12
*  "2018-12-01" = 节点23

## 场景3
sBeginDate = "2015-01-01"
sEndDate = "2015-12-01"

该配置可看成与场景1一致；场景1的配置效率更高
*  "2014-01-01" = 节点0
*  "2014-02-01" = 节点1
*  "2015-02-01" = 节点1
*  "2017-01-01" = 节点0
*  "2017-12-01" = 节点11
*  "2018-12-01" = 节点11

该配置可看成是与场景1一致

## 场景4
sBeginDate = "2015-01-01"
sEndDate = "2015-03-01"

该配置标识只有3个节点；很难与月份对应上；平均分散到3个节点上