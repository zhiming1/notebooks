1. **分布式存储：** HDFS 将大文件划分成大小固定的块（默认大小为128 MB或256 MB）并分布式存储在 Hadoop 集群的多个节点上。这样的设计允许系统并行处理大文件，提高数据处理的效率。
2. **块存储：** 文件被分割成块，并且每个块都会被分布式存储在集群中的多个节点上。每个块通常有三个副本，存储在不同的节点上，以提高容错性。
3. **容错性：** HDFS 提供了高度容错性，通过在不同节点上存储数据的多个副本，以防止硬件故障导致的数据丢失。如果某个节点上的数据不可用，可以从其他节点上的副本中恢复。
4. **简单一致性模型：** HDFS 的一致性模型是“写一次，读多次”。一旦数据被写入 HDFS，它几乎是不可变的。新的数据只能通过追加到文件末尾的方式添加，而现有的数据不能被修改。
5. **大数据处理：** HDFS 是 Apache Hadoop 处理大规模数据集的核心组件之一。它为 MapReduce 任务提供了高效的数据存储和读取。
6. **数据复制：** 为了提高容错性，每个数据块默认情况下会有三个副本分布在集群的不同节点上。这样，即使某个节点发生故障，仍然可以从其他节点上的副本中访问数据。



1. No Hadoop Dependency available
2. Hadoop is not in the classpath/dependencies. The extended set of supported File Systems via Hadoop is not available.
3. Cannot create Hadoop Security Module because Hadoop cannot be found in the Classpath.
4. Cannot install HadoopSecurityContext because Hadoop cannot be found in the Classpath.
5.  Hadoop FS is not available (not packaged with this application): NoClassDefFoundError : "org/apache/hadoop/conf/Configuration".
6.  No tokens obtained so skipping notifications
7. Tokens update task not started because either no tokens obtained or none of the tokens specified its renewal date

- 

"Fine-tune"（微调）是深度学习领域中的一个常见术语

midjourney ai制图工具

![image-20231204214054991](/Users/zhimingyuan/Library/Application Support/typora-user-images/image-20231204214054991.png)