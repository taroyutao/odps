# 什么是MaxCompute {#concept_qbk_1kv_tdb .concept}

大数据计算服务（MaxCompute，原名ODPS）是一种快速、完全托管的TB/PB级数据仓库解决方案。

当今社会数据收集手段不断丰富，行业数据大量积累，数据规模已增长到了传统软件行业无法承载的海量数据（百GB、TB乃至PB）级别。MaxCompute服务于批量结构化数据的存储和计算，提供海量数据仓库的解决方案及分析建模服务。

由于单台服务器的处理能力有限，海量数据的分析需要分布式计算模型。分布式的计算模型对数据分析人员要求较高且不易维护：数据分析人员不仅需要了解业务需求，同时还需要熟悉底层分布式计算模型。MaxCompute为您提供完善的数据导入方案以及多种经典的分布式计算模型，助您快速解决海量数据的计算问题，有效降低企业成本并保障数据安全。您可以不必关心分布式计算和维护细节，便可轻松完成大数据分析。

**说明：** MaxCompute已经在阿里巴巴集团内部得到大规模应用，例如大型互联网企业的数据仓库和BI分析、网站的日志分析、电子商务网站的交易分析、用户特征和兴趣挖掘等。

DataWorks和MaxCompute关系紧密：DataWorks为MaxCompute提供一站式的数据同步、业务流程设计、数据开发、管理和运维功能，详情请参见[DataWorks](https://www.alibabacloud.com/help/doc-detail/30256.htm)。

## MaxCompute学习路径 {#section_learningpath .section}

您可以通过[MaxCompute学习路径](https://www.alibabacloud.com/getting-started/learningpath/maxcompute)快速了解MaxCompute的相关概念、基础操作、进阶操作等。

## 产品优势 {#section_ufc_wrv_tdb .section}

-   大规模计算存储

    MaxCompute适用于100GB以上规模的存储及计算需求，最大可达EB级别。

-   多种计算模型

    MaxCompute支持SQL、MapReduce、Graph等计算类型及MPI迭代类算法。

-   强数据安全

    MaxCompute已稳定支撑阿里全部离线分析业务7年以上，提供多层沙箱防护及监控。

-   低成本

    与企业自建专有云相比，MaxCompute的计算存储更高效，可以降低20%-30%的采购成本。


## 功能概述 {#section_cnm_c5v_tdb .section}

-   数据通道
    -   [批量、历史数据通道](../../../../../intl.zh-CN/用户指南/数据上传下载/数据上传下载概述.md#)

        [TUNNEL](../../../../../intl.zh-CN/用户指南/数据上传下载/批量数据通道SDK介绍/批量数据通道概要.md)是MaxCompute为您提供的数据传输服务，提供高并发的离线数据上传下载服务。支持每天TB/PB级别的数据导入导出，特别适合于全量数据或历史数据的批量导入。Tunnel 为您提供Java编程接口，并且在MaxCompute的客户端工具中，有对应的命令实现本地文件与服务数据的互通。

    -   [实时、增量数据通道](../../../../../intl.zh-CN/用户指南/数据上传下载/DataHub实时数据通道.md#)

        针对实时数据上传的场景，MaxCompute提供了延迟低、使用方便的DataHub服务，特别适用于增量数据的导入。DataHub还支持多种数据传输插件，例如Logstash、Flume、Fluentd、Sqoop等，同时支持日志服务Log Service中的投递日志到MaxCompute，进而使用DataWorks进行日志分析和挖掘。

-   计算及分析任务

    MaxCompute支持多种计算模型，详情如下。

    -   [SQL](../../../../../intl.zh-CN/用户指南/SQL/SQL概述.md#)：MaxCompute以表的形式存储数据，支持多种[数据类型](../../../../../intl.zh-CN/用户指南/基本概念/数据类型.md#)，并对外提供SQL查询功能。您可以将MaxCompute作为传统的数据库软件操作，但其却能处理TB、PB级别的海量数据。

**说明：** 

-   MaxCompute SQL不支持事务、索引及Update/Delete等操作。
-   MaxCompute的SQL语法与Oracle、MySQL有一定差别，您无法将其他数据库中的SQL语句无缝迁移到MaxCompute上来。
-   在使用方式上，MaxCompute SQL最快可以在分钟、乃至秒级别完成查询，无法在毫秒级别返回结果。
-   MaxCompute SQL的优点是学习成本低，您不需要了解复杂的分布式计算概念。如果您具备数据库操作经验，便可快速熟悉MaxCompute SQL的使用。
    -   [UDF](../../../../../intl.zh-CN/用户指南/SQL/UDF/UDF概述.md)：即用户自定义函数。

        MaxCompute提供了很多[内建函数](../../../../../intl.zh-CN/用户指南/SQL/内建函数/日期函数.md)来满足您的计算需求，同时您还可以通过创建自定义函数来满足不同的计算需求。

    -   [MapReduce](../../../../../intl.zh-CN/用户指南/MapReduce/概要/MapReduce概述.md)：MaxCompute MapReduce是MaxCompute提供的Java MapReduce编程模型，它可以简化开发流程，更为高效。您若使用MaxCompute MapReduce，需要对分布式计算概念有基本了解，并有相对应的编程经验。MaxCompute MapReduce为您提供Java编程接口。
    -   [Graph](../../../../../intl.zh-CN/用户指南/图模型/图模型概述.md)：MaxCompute提供的Graph功能是一套面向迭代的图计算处理框架。图计算作业使用图进行建模，图由点 （Vertex）和边（Edge）组成，点和边包含权值（Value）。通过迭代对图进行编辑、演化，最终求解出结果，典型应用：[PageRank](../../../../../intl.zh-CN/用户指南/图模型/示例程序/PageRank.md)、[单源最短距离算法](../../../../../intl.zh-CN/用户指南/图模型/示例程序/单源最短距离.md) 、[K-均值聚类算法](../../../../../intl.zh-CN/用户指南/图模型/示例程序/K-均值聚类.md)等。
-   SDK

    SDK是MaxCompute提供给开发者的工具包，当前支持[Java SDK](../../../../../intl.zh-CN/SDK 参考/Java SDK.md#)及[Python SDK](../../../../../intl.zh-CN/SDK 参考/Python SDK.md#)。

-   安全

    MaxCompute提供了功能强大的安全服务，为您的数据安全提供保护，详情请参见[安全指南](../../../../../intl.zh-CN/安全指南/安全功能详解/目标用户.md)。


## 后续步骤 {#section_akn_wvv_tdb .section}

现在，您已经学习了MaxCompute的产品优势、功能特性等相关简介，您可以继续学习下一个教程。在该教程中您将了解MaxCompute的相关收费情况，详情请参见[产品定价](https://www.alibabacloud.com/help/doc-detail/74873.htm)。

