# Amazon CloudWatch metrics for Amazon RDS<a name="rds-metrics"></a>

The `AWS/RDS` namespace in Amazon CloudWatch includes the following metrics\.

**Note**  
The Amazon RDS console might display metrics in units that are different from the units sent to Amazon CloudWatch\. For example, the Amazon RDS console might display a metric in megabytes \(MB\), while the metric is sent to Amazon CloudWatch in bytes\.


| Metric | Console name | Description | Units | 
| --- | --- | --- | --- | 
| BinLogDiskUsage |   **Binary Log Disk Usage \(MB\)**   |  The amount of disk space occupied by binary logs\. If automatic backups are enabled for MySQL and MariaDB instances, including read replicas, binary logs are created\.  |  Bytes  | 
| BurstBalance |   **Burst Balance \(Percent\)**   |  The percent of General Purpose SSD \(gp2\) burst\-bucket I/O credits available\.   |  Percent  | 
| CPUUtilization |   **CPU Utilization \(Percent\)**   |  The percentage of CPU utilization\.  |  Percent  | 
| CPUCreditUsage |  **CPU Credit Usage \(Count\)**   |  \(T2 instances\) The number of CPU credits spent by the instance for CPU utilization\. One CPU credit equals one vCPU running at 100 percent utilization for one minute or an equivalent combination of vCPUs, utilization, and time\. For example, you might have one vCPU running at 50 percent utilization for two minutes or two vCPUs running at 25 percent utilization for two minutes\. CPU credit metrics are available at a five\-minute frequency only\. If you specify a period greater than five minutes, use the `Sum` statistic instead of the `Average` statistic\.  |  Credits \(vCPU\-minutes\)  | 
| CPUCreditBalance |  **CPU Credit Balance \(Count\)**   | \(T2 instances\) The number of earned CPU credits that an instance has accrued since it was launched or started\. For T2 Standard, the CPUCreditBalance also includes the number of launch credits that have been accrued\.Credits are accrued in the credit balance after they are earned, and removed from the credit balance when they are spent\. The credit balance has a maximum limit, determined by the instance size\. After the limit is reached, any new credits that are earned are discarded\. For T2 Standard, launch credits don't count towards the limit\.The credits in the `CPUCreditBalance` are available for the instance to spend to burst beyond its baseline CPU utilization\.When an instance is running, credits in the `CPUCreditBalance` don't expire\. When the instance stops, the `CPUCreditBalance` does not persist, and all accrued credits are lost\.CPU credit metrics are available at a five\-minute frequency only\. |  Credits \(vCPU\-minutes\)  | 
| DatabaseConnections |  **DB Connections \(Count\)**   |  The number of client network connections to the database instance\. The number of database sessions can be higher than the metric value because the metric value doesn't include the following: [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/rds-metrics.html)  |  Count  | 
| DiskQueueDepth |  **Queue Depth \(Count\)**   |  The number of outstanding I/Os \(read/write requests\) waiting to access the disk\.  |  Count  | 
| EBSByteBalance% |  **EBS Byte Balance \(percent\)**  |  The percentage of throughput credits remaining in the burst bucket of your RDS database\. This metric is available for basic monitoring only\.  To find the instance sizes that support this metric, see the instance sizes with an asterisk \(\*\) in the [EBS optimized by default](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-optimized.html#current) table in *Amazon EC2 User Guide for Linux Instances*\. The `Sum` statistic is not applicable to this metric\.  |  Percent  | 
| EBSIOBalance% |  **EBS IO Balance \(percent\)**  |  The percentage of I/O credits remaining in the burst bucket of your RDS database\. This metric is available for basic monitoring only\. To find the instance sizes that support this metric, see the instance sizes with an asterisk \(\*\) in the [EBS optimized by default](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-optimized.html#current) table in *Amazon EC2 User Guide for Linux Instances*\. The `Sum` statistic is not applicable to this metric\. This metric is different from `BurstBalance`\. To learn how to use this metric, see [Improving application performance and reducing costs with Amazon EBS\-Optimized Instance burst capability](http://aws.amazon.com/blogs/compute/improving-application-performance-and-reducing-costs-with-amazon-ebs-optimized-instance-burst-capability/)\.   |  Percent  | 
| FailedSQLServerAgentJobsCount  |   **Failed SQL Server Agent Jobs Count \(Count/Minute\)**   |  The number of failed Microsoft SQL Server Agent jobs during the last minute\.  |  Count/Minute  | 
| FreeableMemory |   **Freeable Memory \(MB\)**   |  The amount of available random access memory\.  For MariaDB, MySQL, Oracle, and PostgreSQL DB instances, this metric reports the value of the `MemAvailable` field of `/proc/meminfo`\.    |  Bytes  | 
| FreeLocalStorage |   **Free Local Storage \(MB\)**   |  The amount of available local storage space\. Only applies to Multi\-AZ DB clusters\.  |  Bytes  | 
| FreeStorageSpace |   **Free Storage Space \(MB\)**   |  The amount of available storage space\.  |  Bytes  | 
| MaximumUsedTransactionIDs |   **Maximum Used Transaction IDs \(Count\)**   |  The maximum transaction IDs that have been used\. Applies to PostgreSQL\.   |  Count  | 
| NetworkReceiveThroughput |   **Network Receive Throughput \(MB/Second\)**   |  The incoming \(receive\) network traffic on the DB instance, including both customer database traffic and Amazon RDS traffic used for monitoring and replication\.  |  Bytes/Second  | 
| NetworkTransmitThroughput |   **Network Transmit Throughput \(MB/Second\)**   |  The outgoing \(transmit\) network traffic on the DB instance, including both customer database traffic and Amazon RDS traffic used for monitoring and replication\.  |  Bytes/Second  | 
| OldestReplicationSlotLag |   **Oldest Replication Slot Lag \(MB\)**   |  The lagging size of the replica lagging the most in terms of write\-ahead log \(WAL\) data received\. Applies to PostgreSQL\.  |  Bytes  | 
| ReadIOPS |   **Read IOPS \(Count/Second\)**   |  The average number of disk read I/O operations per second\.  |  Count/Second  | 
| ReadIOPSLocalStorage |   **Read IOPS Local Storage \(Count/Second\)**   |  The average number of disk read I/O operations to local storage per second\. Only applies to Multi\-AZ DB clusters\.  |  Count/Second  | 
| ReadLatency |   **Read Latency \(Milliseconds\)**   |  The average amount of time taken per disk I/O operation\.  |  Seconds  | 
| ReadLatencyLocalStorage |   **Read Latency Local Storage \(Milliseconds\)**   |  The average amount of time taken per disk I/O operation for local storage\. Only applies to Multi\-AZ DB clusters\.  |  Seconds  | 
| ReadThroughput |   **Read Throughput \(MB/Second\)**   |  The average number of bytes read from disk per second\.  |  Bytes/Second  | 
| ReadThroughputLocalStorage |   **Read Throughput Local Storage \(MB/Second\)**   |  The average number of bytes read from disk per second for local storage\. Only applies to Multi\-AZ DB clusters\.  |  Bytes/Second  | 
| ReplicaLag |   **Replica Lag \(Milliseconds\)**   |  For read replica configurations, the amount of time a read replica DB instance lags behind the source DB instance\. Applies to MariaDB, Microsoft SQL Server, MySQL, Oracle, and PostgreSQL read replicas\. For Multi\-AZ DB clusters, the difference in time between the latest transaction on the writer DB instance and the latest applied transaction on a reader DB instance\.  |  Seconds  | 
| ReplicationSlotDiskUsage |   **Replica Slot Disk Usage \(MB\)**   |  The disk space used by replication slot files\. Applies to PostgreSQL\.  |  Bytes  | 
| SwapUsage |   **Swap Usage \(MB\)**   |  The amount of swap space used on the DB instance\. This metric is not available for SQL Server\.  |  Bytes  | 
| TransactionLogsDiskUsage |   **Transaction Logs Disk Usage \(MB\)**   |  The disk space used by transaction logs\. Applies to PostgreSQL\.  |  Bytes  | 
| TransactionLogsGeneration |   **Transaction Logs Generation \(MB/Second\)**   |  The size of transaction logs generated per second\. Applies to PostgreSQL\.  |  Bytes/Second  | 
| WriteIOPS |   **Write IOPS \(Count/Second\)**   |  The average number of disk write I/O operations per second\.  |  Count/Second  | 
| WriteIOPSLocalStorage |   **Write IOPS Local Storage \(Count/Second\)**   |  The average number of disk write I/O operations per second on local storage in a Multi\-AZ DB cluster\.  |  Count/Second  | 
| WriteLatency |   **Write Latency \(Milliseconds\)**   |  The average amount of time taken per disk I/O operation\.  |  Seconds  | 
| WriteLatencyLocalStorage |   **Write Latency Local Storage \(Milliseconds\)**   |  The average amount of time taken per disk I/O operation on local storage in a Multi\-AZ DB cluster\.  |  Milliseconds  | 
| WriteThroughput |   **Write Throughput \(MB/Second\)**   |  The average number of bytes written to disk per second\.  |  Bytes/Second  | 
| WriteThroughputLocalStorage |   **Write Throughput Local Storage \(MB/Second\)**   |  The average number of bytes written to disk per second for local storage\.  |  Bytes/Second  | 