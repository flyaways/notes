# 一、数据库索引理论
| 时间 | 名称 | 优点 | 缺点 | 使用场景 | 提出人 |
|------|------|------|------|----------|--------|
| 1970 | B-tree | 平衡树，高效的增删查改 | 大量写入时重平衡成本高 | 广泛用于数据库索引 | Rudolf Bayer, Edward M. McCreight |
| 1972 | AVL tree | 高度平衡，查找速度快 | 插入和删除操作复杂 | 内存中的查找结构 | G.M. Adelson-Velsky and E.M. Landis |
| 1977 | Hash index | 快速查找，常数时间复杂度 | 不支持范围查询，冲突处理复杂 | 键值存储，等值查找 | 不详 |
| 1984 | B+ tree | 优化磁盘I/O，支持顺序访问 | 更新成本相对较高 | 文件系统和数据库 | Douglas Comer |
| 1987 | R-tree | 空间数据索引，支持多维数据 | 更新复杂，可能不平衡 | 地理信息系统 | Antonin Guttman |
| 1990 | Bitmap index | 低基数数据高效，占用空间少 | 高基数数据时效率低 | 数据仓库 | 不详 |
| 1993 | T-tree | 内存中索引，空间效率高 | 不适合磁盘存储，不平衡 | 内存数据库 | Tore Risch |
| 1994 | Patricia trie | 空间效率，支持快速查找 | 较复杂，更新成本高 | 路由查找，字符串检索 | Donald R. Morrison |
| 1996 | GiST | 通用索引，可定制 | 实现复杂 | 扩展性数据库系统 | Joseph M. Hellerstein, Jeffrey F. Naughton, Avi Pfeffer |
| 2000 | Skip list | 平均性能好，实现简单 | 空间使用不如平衡树 | 并发系统 | William Pugh |
| 2003 | Bloom filter | 空间效率，插入和查询快速 | 有一定误判率，不支持删除 | 快速存在性检查 | Burton H. Bloom |
| 2004 | LSM-tree | 写入效率高，适合大量数据 | 读取和更新可能较慢 | NoSQL数据库 | Patrick O'Neil, Edward Cheng, Dieter Gawlick, Elizabeth O'Neil |
| 2005 | Quadtree | 空间划分直观，多维数据索引 | 数据分布不均时效率下降 | 空间数据库 | 不详 |
| 2008 | Covering index | 可以直接返回结果，避免表访问 | 索引大小大 | 查询优化 | 不详 |
| 2010 | Fractal tree | 写入优化，高I/O效率 | 较新的技术，普及度不高 | 数据库存储引擎 | 不详 |
| 2012 | Column-store index | 查询速度快，压缩率高 | 写入更新成本高 | 数据仓库，OLAP | 不详 |
| 2015 | Inverted index | 文本检索高效 | 更新成本高 | 搜索引擎 | 不详 |
| 2017 | Adaptive Radix Tree (ART) | 空间和性能优化 | 相对较新，较少实际应用 | 内存数据库 | Viktor Leis, Alfons Kemper, Thomas Neumann |
| 2019 | Z-order index | 支持多维数据和范围查询 | 某些查询效率不如专门的空间索引 | 多维数据查询 | 不详 |
| 2021 | HTAP index | 支持混合事务/分析处理 | 实现和维护复杂 | 混合工作负载数据库 | 不详 |
| 2022 | Bw-tree | 锁自由，高性能并发控制 | 实现复杂，维护成本高 | 高并发数据库系统 | Microsoft Research |
| 2022 | Succinct Trie | 空间高效，支持快速检索 | 实现复杂，可更新性问题 | 大规模数据集的字符串索引 | 不详 |
| 2023 | Learned index | 自适应，可能超越传统索引 | 依赖数据分布，可解释性差 | 数据库索引，机器学习集成 | Kraska et al. |



# 二、开源数据库
| 开源时间 | 名称                | 索引类型          | 缺点                           | 简介                                                         | 用户和场景                                                   | 开源公司/组织                  |
|----------|---------------------|------------------|--------------------------------|--------------------------------------------------------------|--------------------------------------------------------------|---------------------------------|
| 1995     | MySQL               | B树              | 性能下降随着扩展性增加         | 广泛使用的关系数据库管理系统                                | 网站后端、小型到中型数据库应用                               | Oracle Corporation (原始开源者为MySQL AB) |
| 1996     | PostgreSQL          | B树、GiST、GIN等 | 相对复杂的配置和管理           | 功能丰富的企业级开源关系数据库                              | 企业数据库、复杂查询                                         | PostgreSQL Global Development Group |
| 2000     | SQLite              | B树              | 不适合高并发写操作             | 嵌入式关系数据库，轻量级                                    | 嵌入式设备、移动应用、小型项目                              | D. Richard Hipp                   |
| 2004     | Apache Derby        | B树              | 性能受限于Java环境             | 基于Java的轻量级嵌入式关系数据库                            | 嵌入式系统、小型Java应用                                    | Apache Software Foundation     |
| 2005     | CouchDB             | B树              | 查询速度相对慢                 | 面向文档的NoSQL数据库，支持RESTful HTTP API                | 文档存储、Web应用、本地存储                                   | Apache Software Foundation     |
| 2008     | Apache Cassandra    | SSTable          | 配置复杂、维护成本高            | 高可用性和可扩展性的NoSQL数据库                             | 大规模数据存储、高写入吞吐量                                 | Apache Software Foundation     |
| 2009     | MongoDB             | B树              | 写入安全和数据一致性问题       | 文档导向的NoSQL数据库                                       | 大规模应用、实时分析、快速迭代                               | MongoDB Inc.                    |
| 2009     | Redis               | 无（键值存储）   | 数据量受内存大小限制           | 键值存储数据库，支持多种数据结构                            | 缓存、消息队列、快速事务                                     | Redis Labs (原始开源者为Salvatore Sanfilippo) |
| 2010     | Neo4j               | 图               | 复杂查询可能会有性能问题       | 图形数据库，优化了连接数据的查询                            | 社交网络、推荐系统、知识图谱                                 | Neo4j, Inc.                      |
| 2011     | OrientDB            | 多模型           | 较小的社区和生态系统           | 支持图形和文档的多模型数据库                                | 多模型数据存储、图形查询                                     | Orient Technologies             |
| 2011     | Riak                | 键值             | 开发和维护社区较小             | 分布式NoSQL键值存储数据库                                   | 分布式应用、容错存储                                         | Basho Technologies              |
| 2012     | Apache HBase        | LSM树            | 学习曲线陡峭、管理复杂         | 基于Hadoop的分布式、可扩展的大型数据库                      | 实时读写大规模数据集                                         | Apache Software Foundation     |
| 2013     | InfluxDB            | LSM树            | 查询语言学习曲线               | 面向时间序列数据的数据库                                    | 监控、IoT、实时分析                                          | InfluxData                      |
| 2013     | RethinkDB           | B树              | 社区较小，生态系统有限         | 实时推送的NoSQL文档数据库                                   | 实时Web应用、实时分析                                        | The Linux Foundation (原开源者为RethinkDB, Inc.) |
| 2014     | Apache Couchbase    | B树              | 需要优化以支持大规模部署       | 分布式NoSQL文档数据库                                       | 交互式应用、移动同步                                         | Couchbase, Inc.                 |
| 2014     | CockroachDB         | B树              | 管理和调优可能复杂             | 分布式SQL数据库，强调一致性和容错                           | 分布式事务、全球部署                                         | Cockroach Labs                  |
| 2015     | Apache Kudu         | 列存储           | 需要特定硬件优化               | 为快速分析和高吞吐量的工作负载提供存储                      | 快速数据扫描和高速写入                                       | Apache Software Foundation     |
| 2015     | RocksDB             | LSM树            | 需要精细的调优                 | 高性能嵌入式数据库，由Facebook开发                          | 存储引擎、高性能的本地存储                                   | Facebook                        |
| 2016     | Apache Ignite       | B+树             | 高内存消耗                     | 内存中数据网格和计算平台                                    | 高性能计算、实时处理、内存中数据管理                         | Apache Software Foundation     |
| 2017     | TimescaleDB         | B树              | 依赖PostgreSQL，可能限制创新   | 基于PostgreSQL的时间序列数据库                              | 时间序列数据、物联网、监控                                   | Timescale Inc.                  |
| 2017     | YugaByte DB         | DocDB（基于RocksDB） | 相对较新，社区规模小           | 分布式SQL和NoSQL数据库                                      | 云原生应用、分布式SQL                                        | YugaByte, Inc.                  |
| 2018     | Apache Druid        | 列存储           | 存储和查询优化的复杂性         | 用于大规模事件驱动数据的实时分析                            | 实时分析、大数据可视化                                       | Apache Software Foundation     |
| 2018     | QuestDB             | 列存储           | 社区相对较新                   | 高性能的时间序列数据库                                      | 高频交易、实时分析、大规模监控                               | QuestDB Ltd.                    |
| 2019     | Prisma              | 无（ORM框架）   | 依赖于Node.js生态系统           | 服务器端库，用于在Node.js和TypeScript中处理数据库工作        | Web应用、服务器端应用                                        | Prisma                          |
| 2020     | VictoriaMetrics     | 列存储           | 相对较新，文档和社区正在成长   | 高性能、可扩展的时间序列数据库                              | 监控解决方案、时间序列数据分析                               | VictoriaMetrics Inc.            |
| 2020     | DuckDB              | 列存储           | 社区和生态系统相对较新         | 嵌入式分析数据库                                            | 分析工作负载、数据科学                                       | CWI Database Architectures      |
| 2021     | TerminusDB          | 图               | 相对较新，社区正在成长中       | 为数据密集型应用设计的图形数据库                            | 数据集成、版本控制、协作数据管理                             | TerminusDB                      |
| 2022     | Trino               | 无（分布式SQL查询引擎）| 依赖其他数据存储系统           | 分布式SQL查询引擎，用于大数据分析                           | 数据湖查询、分析跨多个数据存储                               | Trino Software Foundation       |
| 2022     | OceanBase           | B树              | 相对较新，社区规模较小         | 阿里巴巴开发的企业级分布式关系数据库                        | 金融服务、高可用性需求的企业级应用                           | Alibaba Group                    |
| 2022     | PolarDB             | B树              | 云服务依赖                     | 阿里云提供的云原生关系数据库服务                            | 适用于需要弹性和高性能数据库服务的云应用                     | Alibaba Cloud                    |
| 2023     | EdgeDB              | 自定义           | 相对较新，初学者学习曲线       | 结合了图形和关系模型的下一代数据库                          | 开发现代应用，需要高级查询能力和数据关系的场景               | EdgeDB Inc.                      |
| 2023     | Noria               | 自定义           | 研究阶段，尚未广泛采用         | 基于数据流的数据库系统，旨在自动优化查询                    | 需要快速读取操作的Web应用                                   | MIT CSAIL                        |
