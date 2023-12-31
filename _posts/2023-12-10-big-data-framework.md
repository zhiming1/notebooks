---
layout: post
title: 大数据模型
categories: [大数据模型，hadoop+hive+spark]
description: 大数据模型
keywords: 大数据模型
---



![](https://raw.githubusercontent.com/zhiming1/blog_pictures/main/blog/img202311270044013.png)

**图中涉及的技术名词解释如下：**

1. Sqoop：Sqoop 是一款开源的工具，主要用于在Hadoop、Hive 与传统的数据库（MySQL）间进行数据的传递，可以将一个关系型数据库（例如 ：MySQL，Oracle 等）中的数据导进到Hadoop 的HDFS 中，也可以将HDFS 的数据导进到关系型数据库中。
2. Flume：Flume 是一个高可用的，高可靠的，分布式的海量日志采集、聚合和传输的系统，Flume 支持在日志系统中定制各类数据发送方，用于收集数据。
3. Kafka：Kafka 是一种高吞吐量的分布式发布订阅消息系统。
4. Spark：Spark 是当前最流行的开源大数据内存计算框架。可以基于Hadoop 上存储的大数据进行计算。
5. Flink：Flink 是当前最流行的开源大数据内存计算框架。用于实时计算的场景较多。
6. Oozie：Oozie 是一个管理Hadoop 作业（job）的工作流程调度管理系统。
7. Hbase：HBase 是一个分布式的、面向列的开源数据库。HBase 不同于一般的关系数据库，它是一个适合于非结构化数据存储的数据库。
8. Hive：Hive 是基于Hadoop 的一个数据仓库工具，可以将结构化的数据文件映射为一张数据库表，并提供简单的SQL 查询功能，可以将SQL 语句转换为MapReduce 任务进行运行。其优点是学习成本低，可以通过类SQL 语句快速实现简单的MapReduce 统计，不必开发专门的MapReduce 应用，十分适合数据仓库的统计分析。
9. ZooKeeper：它是一个针对大型分布式系统的可靠协调系统，提供的功能包括：配置维护、名字服务、分布式同步、组服务等。

