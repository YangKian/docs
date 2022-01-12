# HStreamDB 功能特性

*注：以下功能特性为到 HStreamDB 1.0 版本为止的全部规划，部分功能正在持续开发中，当前版本暂未实现，敬请期待*。

![](https://static.emqx.net/images/ca810cdf1d13ffbc1fe15ce41daa1695.png)

<center>HStreamDB 功能架构</center>

## 基于 SQL 的数据流处理

HStreamDB 设计了完整的基于事件时间的状态化处理方案，不仅支持基本的过滤、转换操作，还支持按 key 做聚合计算，基于多种时间窗口的计算，以及数据流之间 join 的能力，同时也支持乱序和晚到的消息的特殊处理，保证计算结果的准确性。用户只需要通过 SQL 语句就能完成上述所有的处理功能，无需学习任何三方 API。同时，HStream 的流处理具备丰富的扩展能力，用户可以针对自己的业务自行扩展。

## 数据流的物化查询

HStreamDB 提供物化视图功能，支持在持续更新的数据流上进行复杂的查询和分析操作。 HStreamDB 内部的增量计算引擎会根据数据流的变化实时更新物化视图，用户可通过 SQL 语句查询物化视图获得实时的数据洞察。

## 数据流管理

HStreamDB 支持创建和管理大量的数据流， 数据流的创建在 HStreamDB 是非常轻量的操作， 同时基于优化的存储设计， 在大量数据流并发读写的情况下仍然能够保持稳定的读写延迟。

## 数据流的持久化存储

HStreamDB 提供低延时的可靠的数据流存储，保证写入的数据消息不丢失，并且能够重复消费。HStreamDB 会将写入的数据消息复制到多个存储节点，提供高可用和容错能力，同时支持将冷数据转储到成本更低的存储服务上，比如对象存储、分布式文件存储等，存储的容量可无限扩展，能够实现数据的永久存储。

## 数据流的 Schema 管理

HStreamDB 强调弹性的 Schema 支持，数据流可以是无 Schema 的，也可以通过 Json、 Avro、Protobuf 等多种格式来制定 Schema， 同时也支持 Schema 的演化，自动管理多版本 Schema 之间的兼容性。

## 数据流的接入和分发

HStreamDB 数据的接入和分发由 Connector 完成，它与包括 MQTT Broker、MySQL、ElasticSearch、Redis 等在内的多种数据系统相连接，方便用户和外部数据系统进行集成。

## 安全机制

HStreamDB 的安全性将由 TLS 加密传输、基于 OAuth 和 JWT 等的身份认证以及授权机制保证，同时预留安全插件接口，用户可根据需要对默认的安全机制进行扩展。

## 监控和运维工具

HStreamDB 设置了基于 Web 的控制台，包含大量的系统仪表盘和可视化图表， 能够对集群机器状态，系统关键指标等进行详细的监控，方便运维人员对集群进行管理。