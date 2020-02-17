---
title: 图数据库 Nebula Graph v.1.0.0-beta 已上线
date: 2019-08-20
---

#  图数据库 Nebula Graph v.1.0.0-beta 已上线

![beta](https://user-images.githubusercontent.com/56643819/72507383-c2980980-387e-11ea-850e-0ab644f464c7.png)

> [Nebula Graph](https://github.com/vesoft-inc/nebula "Nebula Graph")：一个开源的分布式图数据库。作为唯一能够存储万亿个带属性的节点和边的在线图数据库，Nebula Graph 不仅能够在高并发场景下满足毫秒级的低时延查询要求，还能够实现服务高可用且保障数据安全性。

Nebula Graph **v1.0.0-beta** 版本已发布，更新内容如下:

### Storage Engine

- 支持集群部署
- 引入 Raft 一致性协议，支持 Leader 切换
- 存储引擎支持 HBase
- 新增从 HDFS 导入数据功能

### 查询语言 nGQL

- 新增注释功能
- 创建 Space 支持默认属性，新增 `SHOW SPACE` 和 `DROP SPACE` 功能
- 新增获取某 Tag 或 EdgeType 属性功能
- 新增获取某 Tag 或 EdgeType 列表功能
- 新增 `DISTINCT` 过滤重复数据
- 新增 `UNION` ， `INTERSECT` 和 `MINUS` 集合运算
- 新增 `FETCH` 获取指定 Vertex 相应 Tag 的属性值
- `WHERE` 和 `YIELD` 支持用户定义变量和管道操作
- `WHERE` 和 `YIELD` 支持算术和逻辑运算
- 新增 `ORDER BY` 对结果集排序
- 支持插入多条点或边
- 支持 HOSTS 的 CRUD 操作

### Tools

- 新增 Java importer - 从 CSV 导入数据
- package_build -  支持 Linux 发行指定版本的软件包
- perf tool - Storage Service 压测工具
- Console 支持关键字自动补全功能

### ChangeLog

- `$$[tag].prop` 变更为 `$$.tag.prop` ， `$^[tag].prop` 变更为 `$^.tag.prop` 
- 重构运维脚本 nebula.service

### 附录
最后是 Nebula 的 GitHub 地址，欢迎大家试用，有什么问题可以向我们提 issue。GitHub 地址：[https://github.com/vesoft-inc/nebula](https://github.com/vesoft-inc/nebula)  ；加入 Nebula Graph 交流群，请联系 Nebula Graph 官方小助手微信号：NebulaGraphbot
