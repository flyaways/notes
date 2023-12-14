| 开源时间 | 数据库名称  | 支持的索引类型 | 开源公司/组织                          | 数据库简介                                     | 用户和场景                      |
|----------|-------------|-----------------|----------------------------------------|------------------------------------------------|---------------------------------|
| 1995     | MySQL       | B-tree, Hash    | Oracle Corporation (Originally MySQL AB) | 广泛使用的关系数据库，适用于各种应用           | 网站后端、企业数据库            |
| 1996     | PostgreSQL  | B-tree, GiST    | PostgreSQL Global Development Group   | 功能强大的对象关系数据库                       | 企业级应用、复杂查询、GIS       |
| 2000     | SQLite      | B-tree          | D. Richard Hipp (Independent)         | 轻量级、嵌入式、高可靠性数据库                 | 移动应用、桌面应用              |
| 2000     | Firebird    | B-tree          | Firebird Foundation                   | 基于InterBase的关系数据库                      | 中小型企业、独立软件开发者      |
| 2003     | Berkley DB  | B-tree, Hash    | Oracle Corporation                    | 嵌入式键/值数据库                              | 嵌入式系统、IoT设备             |
| 2004     | Apache Solr | Inverted        | Apache Software Foundation            | 基于Lucene的企业搜索平台                       | 企业级搜索、大数据分析          |
| 2005     | Apache Derby| B-tree          | Apache Software Foundation            | 嵌入式关系数据库管理系统                       | 移动应用、嵌入式系统            |
| 2005     | Apache CouchDB | B-tree        | Apache Software Foundation            | 面向文档的NoSQL数据库                          | Web应用、移动设备               |
| 2006     | Percona Server | B-tree, Hash  | Percona LLC                           | MySQL的增强版，提供更好的性能和监控            | 高性能在线事务处理 (OLTP) 系统  |
| 2007     | Neo4j       | B-tree, Full-text | Neo4j, Inc.                           | 图数据库，优化了连接数据的查询                 | 社交网络、推荐系统              |
| 2008     | Cassandra   | LSM Tree        | Apache Software Foundation            | 分布式NoSQL数据库                              | 高可扩展性和高可用性的场景      |
| 2009     | MongoDB     | B-tree, Inverted | MongoDB Inc.                          | 面向文档的NoSQL数据库                          | Web应用、大数据、实时分析       |
| 2009     | Redis       | Hash, Sorted Set | Redis Labs                            | 内存数据结构存储，支持多种数据类型             | 缓存、消息队列、实时分析        |
| 2009     | MariaDB     | B-tree, Aria     | MariaDB Foundation                    | MySQL的分支，注重开源和社区                    | 替代MySQL，提供更多功能         |
| 2010     | Apache HBase | LSM Tree        | Apache Software Foundation            | 面向列的NoSQL数据库，适用于Hadoop生态系统      | 大数据存储和分析                |
| 2010     | Riak        | LSM Tree        | Basho Technologies                    | 分布式NoSQL数据库                              | 高可用性和容错性场景            |
| 2010     | Elasticsearch | Inverted       | Elastic NV                            | 搜索引擎，优化了搜索和分析                     | 日志分析、全文搜索              |
| 2011     | OrientDB    | LSM Tree, SB-tree | Orient Technologies                   | 多模型数据库                                   | 多模型数据存储、数据关联分析    |
| 2011     | Apache Accumulo | LSM Tree      | Apache Software Foundation            | 分布式键/值存储，强调安全性                    | 需要安全性和高可扩展性的应用    |
| 2012     | PouchDB     | B-tree          | Apache Software Foundation            | 浏览器中的NoSQL数据库，与CouchDB同步           | 离线应用、移动应用              |
| 2012     | Apache Cassandra | LSM Tree    | Apache Software Foundation            | 分布式NoSQL数据库                              | 高可扩展性和高性能的场景        |
| 2013     | InfluxDB    | B-tree, TSI     | InfluxData                            | 面向时序数据的数据库                           | 监控、物联网、实时分析          |
| 2013     | LevelDB     | LSM Tree        | Google                                | 轻量级键/值数据库，适用于嵌入式系统           | 嵌入式系统、数据缓存            |
| 2013     | RocksDB     | LSM Tree        | Facebook                              | 嵌入式键/值数据库，优化了快速存储             | 高性能场景、存储引擎            |
| 2014     | CockroachDB | B-tree          | Cockroach Labs                        | 分布式SQL数据库，保证事务一致性                | 分布式系统、金融服务            |
| 2015     | RethinkDB   | B-tree          | The Linux Foundation                  | 开源分布式文档存储数据库                       | 实时Web应用                     |
| 2015     | Apache Kudu | LSM Tree        | Apache Software Foundation            | 面向分析的存储系统，适用于Hadoop生态系统       | 快速分析、数据仓库              |
| 2015     | ArangoDB    | Hash, Skiplist  | ArangoDB Inc.                         | 多模型数据库，支持文档、图形和键值             | 多模型数据存储、复杂查询        |
| 2015     | Apache TinkerPop | N/A          | Apache Software Foundation             | 图计算框架，支持多种图数据库                    | 图形数据分析、数据科学            |
| 2015     | CrateDB      | B-tree, Full-text | Crate.io                              | 分布式SQL数据库，优化了大数据和IoT               | 大数据分析、物联网                |
| 2016     | Apache Flink | N/A             | Apache Software Foundation             | 流处理框架，包含存储系统                        | 实时数据处理、事件驱动应用        |
| 2016     | Apache Ignite | B-tree, Geospatial | Apache Software Foundation          | 内存中数据网格和缓存，支持SQL查询               | 高性能计算、实时分析              |
| 2016     | YugaByte DB  | LSM Tree, DocDB | YugaByte, Inc.                         | 分布式SQL和NoSQL数据库                          | 云原生应用、分布式应用            |
| 2017     | TimescaleDB  | B-tree          | Timescale                              | 基于PostgreSQL的时序数据库                      | 时间序列数据、物联网              |
| 2017     | JanusGraph   | B-tree, Inverted | Linux Foundation                      | 可扩展的图数据库                                | 大规模图形分析、知识图谱          |
| 2018     | Apache Druid | Bitmap, B-tree  | Apache Software Foundation             | 面向实时分析的分布式数据存储                    | 实时分析、大数据可视化            |
| 2018     | QuestDB      | B-tree          | QuestDB Limited                        | 高性能时序数据库                                | 金融服务、监控、物联网           |
| 2018     | VictoriaMetrics | LSM Tree     | VictoriaMetrics Inc.                   | 时序数据库和监控解决方案                        | 监控、时序数据分析               |
| 2019     | Prisma       | N/A             | Prisma                                | 数据库工具套件，简化数据库访问                  | 应用开发、ORM                    |
| 2019     | TerminusDB   | Graph, Inverted | TerminusDB                            | 版本控制图数据库                                | 数据集成、协作数据管理           |
| 2020     | DuckDB       | B-tree          | CWI and DuckDB Labs                    | 嵌入式分析数据库                                | 分析工作负载、数据科学           |
| 2020     | Nebula Graph | LSM Tree, Raft  | VEsoft Inc.                           | 分布式图数据库                                  | 大规模图数据处理、社交网络       |
| 2021     | Dolt         | B-tree          | DoltHub                                | Git-like 版本控制数据库                         | 数据协作、版本控制                |
| 2021     | PolarDB      | B-tree, LSM Tree | Alibaba Cloud                          | 兼容MySQL和PostgreSQL的云原生数据库服务        | 企业级云数据库、大规模在线服务   |
| 2022     | OceanBase    | B-tree          | Ant Group                              | 分布式关系数据库，专注于金融服务行业的高可用性 | 金融服务、企业级应用             |
| 2022     | Trino        | N/A             | Trino Software Foundation              | 分布式SQL查询引擎                               | 数据湖查询、分析工作负载         |
| 2023     | Noria        | B-tree          | MIT CSAIL                              | 流处理和持久化的数据流数据库                   | 实时应用、Web应用                |
