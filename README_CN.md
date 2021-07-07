# 介绍

Adapter 在上层应用程序和底层引擎之间构建了一层计算中间件。通过使用Adapter 提供的REST/WebSocket/JDBC 等标准接口，上层应用可以方便地连接访问MySQL/Spark/Hive/Presto/Flink 等底层引擎，同时实现变量、脚本、函数和资源文件等用户资源的跨上层应用互通。
作为计算中间件，Adapter 提供了强大的连通、复用、编排、扩展和治理管控能力。通过计算中间件将应用层和引擎层解耦，简化了复杂的网络调用关系，降低了整体复杂度，同时节约了整体开发和维护成本。
Adapter 自2019年开源发布以来，已累计积累了700多家试验企业和1000+沙盒试验用户，涉及金融、电信、制造、互联网等多个行业。许多公司已经将Adapter 作为大数据平台底层计算存储引擎的统一入口，和计算请求/任务的治理管控利器。
 

# 核心特点

- **丰富的底层计算存储引擎支持**。
    **目前支持的计算存储引擎**：Spark、Hive、Python、Presto、ElasticSearch、MLSQL、TiSpark、JDBC和Shell等。
    **正在支持中的计算存储引擎**：Flink、Impala等。
    **支持的脚本语言**：SparkSQL, HiveQL, Python, Shell, Pyspark, R, Scala 和JDBC 等。
- **强大的计算治理能力**。基于Orchestrator、Label Manager和定制的Spring Cloud Gateway等服务，Adapter能够提供基于多级标签的跨集群/跨IDC 细粒度路由、负载均衡、多租户、流量控制、资源控制和编排策略(如双活、主备等)支持能力。
- **全栈计算存储引擎架构支持**。能够接收、执行和管理针对各种计算存储引擎的任务和请求，包括离线批量任务、交互式查询任务、实时流式任务和存储型任务；
- **资源管理能力**。 ResourceManager 不仅具备 Adapter0.X 对 Yarn 和 Adapter EngineManager 的资源管理能力，还将提供基于标签的多级资源分配和回收能力，让 ResourceManager 具备跨集群、跨计算资源类型的强大资源管理能力。
- **统一上下文服务**。为每个计算任务生成context id，跨用户、系统、计算引擎的关联管理用户和系统资源文件（JAR、ZIP、Properties等），结果集，参数变量，函数等，一处设置，处处自动引用；
- **统一物料**。系统和用户级物料管理，可分享和流转，跨用户、系统共享物料。

# 支持的引擎类型

| **引擎**      | **引擎版本**                    | 是否适配 | **说明**                                                                                   |
|:--------------|:--------------------------------|:--------:|:-------------------------------------------------------------------------------------------|
| Flink         | 1.11.0                          |          | Flink EngineConn。支持FlinkSQL 代码，也支持以Flink Jar 形式启动一个新的Yarn 应用程序。     |
| Impala        | \>=3.2.0, CDH >=6.3.0"          |          | Impala EngineConn. 支持Impala SQL 代码.                                                    |
| Presto        | \>= 0.180                       |          | Presto EngineConn. 支持Presto SQL 代码.                                                    |
| ElasticSearch | \>=6.0                          |          | ElasticSearch EngineConn. 支持SQL 和DSL 代码.                                              |
| Shell         | Bash >=2.0                      |          | Shell EngineConn. 支持Bash shell 代码.                                                     |
| MLSQL         | \>=1.1.0                        |          | MLSQL EngineConn. 支持MLSQL 代码.                                                          |
| JDBC          | MySQL >=5.0, Hive >=1.2.1       |          | JDBC EngineConn. 已支持MySQL 和HiveQL，可快速扩展支持其他有JDBC Driver 包的引擎, 如Oracle. |
| Spark         | Apache 2.0.0~2.4.7, CDH >=5.4.0 |          | Spark EngineConn. 支持SQL, Scala, Pyspark 和R 代码.                                        |
| Hive          | Apache >=1.0.0, CDH >=5.4.0     |          | Hive EngineConn. 支持HiveQL 代码.                                                          |
| Hadoop        | Apache >=2.6.0, CDH >=5.4.0     |          | Hadoop EngineConn. 支持Hadoop MR/YARN application.                                         |
| Python        | \>=2.6                          |          | Python EngineConn. 支持python 代码.                                                        |
| TiSpark       | 1.1                             |          | TiSpark EngineConn. 支持用SparkSQL 查询TiDB.                                               |

