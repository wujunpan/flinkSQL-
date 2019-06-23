# flinkSQL可视化功能开发
基于袋鼠云提供的开源flinkStreamSQL项目，对其实时sql进行可视化功能开发；通过tcpip通信，前端页面选择需要连接的数据库信息，并写sql语句，点击提交后，后端自动执行集群启动和JobGraph提交，并返回结果给前端页面。实现了使用者即使不了解Kafka、flink等，不会写flink工程，通过简单的图像化操作，即可实现实时查询。

首先用户在数据库中新建某个表，在表中每条记录包含了address、topic、Schema等字段，address用来指定kafka等地址，topic用来指定数据的位置，Schema是一个list,就指定了kafaka中的字段名称(为了通用性，假设Kafaka里面都是标准的Jeson，都是打平的)。

##Step0:用户打开该界面，后台的CluaterClient提交服务器就开启运行，等待任务提交
Step1：用户在这个表里面添加了各个表存储信息，字段信息
Step2:这些表名称呈现在用户的界面，用户勾选需要进行操作的表（选中的表包括查询的源表以及插入结果的表）
Step3:用户写sql来操作这些选中的表
Step4:用户点击“提交”，执行sql运行程序
