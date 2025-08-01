[comment]: <> (Code generated by mdatagen. DO NOT EDIT.)

# sqlserver

## Default Metrics

The following metrics are emitted by default. Each of them can be disabled by applying the following configuration:

```yaml
metrics:
  <metric_name>:
    enabled: false
```

### sqlserver.batch.request.rate

Number of batch requests received by SQL Server.

| Unit | Metric Type | Value Type |
| ---- | ----------- | ---------- |
| {requests}/s | Gauge | Double |

### sqlserver.batch.sql_compilation.rate

Number of SQL compilations needed.

| Unit | Metric Type | Value Type |
| ---- | ----------- | ---------- |
| {compilations}/s | Gauge | Double |

### sqlserver.batch.sql_recompilation.rate

Number of SQL recompilations needed.

| Unit | Metric Type | Value Type |
| ---- | ----------- | ---------- |
| {compilations}/s | Gauge | Double |

### sqlserver.lock.wait.rate

Number of lock requests resulting in a wait.

| Unit | Metric Type | Value Type |
| ---- | ----------- | ---------- |
| {requests}/s | Gauge | Double |

### sqlserver.lock.wait_time.avg

Average wait time for all lock requests that had to wait.

This metric is only available when running on Windows.

| Unit | Metric Type | Value Type |
| ---- | ----------- | ---------- |
| ms | Gauge | Double |

### sqlserver.page.buffer_cache.hit_ratio

Pages found in the buffer pool without having to read from disk.

| Unit | Metric Type | Value Type |
| ---- | ----------- | ---------- |
| % | Gauge | Double |

### sqlserver.page.checkpoint.flush.rate

Number of pages flushed by operations requiring dirty pages to be flushed.

This metric is only available when running on Windows.

| Unit | Metric Type | Value Type |
| ---- | ----------- | ---------- |
| {pages}/s | Gauge | Double |

### sqlserver.page.lazy_write.rate

Number of lazy writes moving dirty pages to disk.

This metric is only available when running on Windows.

| Unit | Metric Type | Value Type |
| ---- | ----------- | ---------- |
| {writes}/s | Gauge | Double |

### sqlserver.page.life_expectancy

Time a page will stay in the buffer pool.

| Unit | Metric Type | Value Type |
| ---- | ----------- | ---------- |
| s | Gauge | Int |

#### Attributes

| Name | Description | Values | Optional |
| ---- | ----------- | ------ | -------- |
| performance_counter.object_name | Category to which this counter belongs | Any Str | false |

### sqlserver.page.operation.rate

Number of physical database page operations issued.

This metric is only available when running on Windows.

| Unit | Metric Type | Value Type |
| ---- | ----------- | ---------- |
| {operations}/s | Gauge | Double |

#### Attributes

| Name | Description | Values | Optional |
| ---- | ----------- | ------ | -------- |
| type | The page operation types. | Str: ``read``, ``write`` | false |

### sqlserver.page.split.rate

Number of pages split as a result of overflowing index pages.

This metric is only available when running on Windows.

| Unit | Metric Type | Value Type |
| ---- | ----------- | ---------- |
| {pages}/s | Gauge | Double |

### sqlserver.transaction.rate

Number of transactions started for the database (not including XTP-only transactions).

This metric is only available when running on Windows.

| Unit | Metric Type | Value Type |
| ---- | ----------- | ---------- |
| {transactions}/s | Gauge | Double |

### sqlserver.transaction.write.rate

Number of transactions that wrote to the database and committed.

This metric is only available when running on Windows.

| Unit | Metric Type | Value Type |
| ---- | ----------- | ---------- |
| {transactions}/s | Gauge | Double |

### sqlserver.transaction_log.flush.data.rate

Total number of log bytes flushed.

This metric is only available when running on Windows.

| Unit | Metric Type | Value Type |
| ---- | ----------- | ---------- |
| By/s | Gauge | Double |

### sqlserver.transaction_log.flush.rate

Number of log flushes.

This metric is only available when running on Windows.

| Unit | Metric Type | Value Type |
| ---- | ----------- | ---------- |
| {flushes}/s | Gauge | Double |

### sqlserver.transaction_log.flush.wait.rate

Number of commits waiting for a transaction log flush.

This metric is only available when running on Windows.

| Unit | Metric Type | Value Type |
| ---- | ----------- | ---------- |
| {commits}/s | Gauge | Double |

### sqlserver.transaction_log.growth.count

Total number of transaction log expansions for a database.

This metric is only available when running on Windows.

| Unit | Metric Type | Value Type | Aggregation Temporality | Monotonic |
| ---- | ----------- | ---------- | ----------------------- | --------- |
| {growths} | Sum | Int | Cumulative | true |

### sqlserver.transaction_log.shrink.count

Total number of transaction log shrinks for a database.

This metric is only available when running on Windows.

| Unit | Metric Type | Value Type | Aggregation Temporality | Monotonic |
| ---- | ----------- | ---------- | ----------------------- | --------- |
| {shrinks} | Sum | Int | Cumulative | true |

### sqlserver.transaction_log.usage

Percent of transaction log space used.

This metric is only available when running on Windows.

| Unit | Metric Type | Value Type |
| ---- | ----------- | ---------- |
| % | Gauge | Int |

### sqlserver.user.connection.count

Number of users connected to the SQL Server.

| Unit | Metric Type | Value Type |
| ---- | ----------- | ---------- |
| {connections} | Gauge | Int |

## Optional Metrics

The following metrics are not emitted by default. Each of them can be enabled by applying the following configuration:

```yaml
metrics:
  <metric_name>:
    enabled: true
```

### sqlserver.computer.uptime

Computer uptime.

| Unit | Metric Type | Value Type |
| ---- | ----------- | ---------- |
| {seconds} | Gauge | Int |

### sqlserver.cpu.count

Number of CPUs.

| Unit | Metric Type | Value Type |
| ---- | ----------- | ---------- |
| {CPUs} | Gauge | Int |

### sqlserver.database.backup_or_restore.rate

Total number of backups/restores.

| Unit | Metric Type | Value Type |
| ---- | ----------- | ---------- |
| “{backups_or_restores}/s” | Gauge | Double |

### sqlserver.database.count

The number of databases

This metric is only available when the receiver is configured to directly connect to SQL Server.

| Unit | Metric Type | Value Type |
| ---- | ----------- | ---------- |
| {databases} | Gauge | Int |

#### Attributes

| Name | Description | Values | Optional |
| ---- | ----------- | ------ | -------- |
| database.status | The current status of a database | Str: ``online``, ``restoring``, ``recovering``, ``pending_recovery``, ``suspect``, ``offline`` | false |

### sqlserver.database.execution.errors

Number of execution errors.

| Unit | Metric Type | Value Type |
| ---- | ----------- | ---------- |
| “{errors}” | Gauge | Int |

### sqlserver.database.full_scan.rate

The number of unrestricted full table or index scans.

| Unit | Metric Type | Value Type |
| ---- | ----------- | ---------- |
| {scans}/s | Gauge | Double |

### sqlserver.database.io

The number of bytes of I/O on this file.

This metric is only available when the receiver is configured to directly connect to SQL Server.

| Unit | Metric Type | Value Type | Aggregation Temporality | Monotonic |
| ---- | ----------- | ---------- | ----------------------- | --------- |
| By | Sum | Int | Cumulative | true |

#### Attributes

| Name | Description | Values | Optional |
| ---- | ----------- | ------ | -------- |
| physical_filename | The physical filename of the file being monitored. | Any Str | false |
| logical_filename | The logical filename of the file being monitored. | Any Str | false |
| file_type | The type of file being monitored. | Any Str | false |
| direction | The direction of flow of bytes or operations. | Str: ``read``, ``write`` | false |

### sqlserver.database.latency

Total time that the users waited for I/O issued on this file.

This metric is only available when the receiver is configured to directly connect to SQL Server.

| Unit | Metric Type | Value Type | Aggregation Temporality | Monotonic |
| ---- | ----------- | ---------- | ----------------------- | --------- |
| s | Sum | Double | Cumulative | true |

#### Attributes

| Name | Description | Values | Optional |
| ---- | ----------- | ------ | -------- |
| physical_filename | The physical filename of the file being monitored. | Any Str | false |
| logical_filename | The logical filename of the file being monitored. | Any Str | false |
| file_type | The type of file being monitored. | Any Str | false |
| direction | The direction of flow of bytes or operations. | Str: ``read``, ``write`` | false |

### sqlserver.database.operations

The number of operations issued on the file.

This metric is only available when the receiver is configured to directly connect to SQL Server.

| Unit | Metric Type | Value Type | Aggregation Temporality | Monotonic |
| ---- | ----------- | ---------- | ----------------------- | --------- |
| {operations} | Sum | Int | Cumulative | true |

#### Attributes

| Name | Description | Values | Optional |
| ---- | ----------- | ------ | -------- |
| physical_filename | The physical filename of the file being monitored. | Any Str | false |
| logical_filename | The logical filename of the file being monitored. | Any Str | false |
| file_type | The type of file being monitored. | Any Str | false |
| direction | The direction of flow of bytes or operations. | Str: ``read``, ``write`` | false |

### sqlserver.database.tempdb.space

Total free space in temporary DB.

| Unit | Metric Type | Value Type | Aggregation Temporality | Monotonic |
| ---- | ----------- | ---------- | ----------------------- | --------- |
| “KB” | Sum | Int | Cumulative | false |

#### Attributes

| Name | Description | Values | Optional |
| ---- | ----------- | ------ | -------- |
| tempdb.state | The status of the tempdb space usage. | Str: ``free``, ``used`` | false |

### sqlserver.database.tempdb.version_store.size

TempDB version store size.

| Unit | Metric Type | Value Type |
| ---- | ----------- | ---------- |
| “KB” | Gauge | Double |

### sqlserver.deadlock.rate

Total number of deadlocks.

| Unit | Metric Type | Value Type |
| ---- | ----------- | ---------- |
| “{deadlocks}/s” | Gauge | Double |

### sqlserver.index.search.rate

Total number of index searches.

| Unit | Metric Type | Value Type |
| ---- | ----------- | ---------- |
| “{searches}/s” | Gauge | Double |

### sqlserver.lock.timeout.rate

Total number of lock timeouts.

| Unit | Metric Type | Value Type |
| ---- | ----------- | ---------- |
| “{timeouts}/s” | Gauge | Double |

### sqlserver.lock.wait.count

Cumulative count of lock waits that occurred.

This metric is only available when the receiver is configured to directly connect to SQL Server.

| Unit | Metric Type | Value Type | Aggregation Temporality | Monotonic |
| ---- | ----------- | ---------- | ----------------------- | --------- |
| {wait} | Sum | Int | Cumulative | true |

### sqlserver.login.rate

Total number of logins.

| Unit | Metric Type | Value Type |
| ---- | ----------- | ---------- |
| “{logins}/s” | Gauge | Double |

### sqlserver.logout.rate

Total number of logouts.

| Unit | Metric Type | Value Type |
| ---- | ----------- | ---------- |
| “{logouts}/s” | Gauge | Double |

### sqlserver.memory.grants.pending.count

Total number of memory grants pending.

| Unit | Metric Type | Value Type | Aggregation Temporality | Monotonic |
| ---- | ----------- | ---------- | ----------------------- | --------- |
| “{grants}” | Sum | Int | Cumulative | false |

### sqlserver.memory.usage

Total memory in use.

| Unit | Metric Type | Value Type | Aggregation Temporality | Monotonic |
| ---- | ----------- | ---------- | ----------------------- | --------- |
| “KB” | Sum | Double | Cumulative | false |

### sqlserver.os.wait.duration

Total wait time for this wait type

This metric is only available when the receiver is configured to directly connect to SQL Server.

| Unit | Metric Type | Value Type | Aggregation Temporality | Monotonic |
| ---- | ----------- | ---------- | ----------------------- | --------- |
| s | Sum | Double | Cumulative | true |

#### Attributes

| Name | Description | Values | Optional |
| ---- | ----------- | ------ | -------- |
| wait.category | Category of the reason for a wait. | Any Str | false |
| wait.type | Type of the wait, view [WaitTypes documentation](https://learn.microsoft.com/en-us/sql/relational-databases/system-dynamic-management-views/sys-dm-os-wait-stats-transact-sql?view=sql-server-ver16#WaitTypes) for more information. | Any Str | false |

### sqlserver.page.buffer_cache.free_list.stalls.rate

Number of free list stalls.

| Unit | Metric Type | Value Type |
| ---- | ----------- | ---------- |
| “{stalls}/s” | Gauge | Int |

### sqlserver.page.lookup.rate

Total number of page lookups.

| Unit | Metric Type | Value Type |
| ---- | ----------- | ---------- |
| “{lookups}/s” | Gauge | Double |

### sqlserver.processes.blocked

The number of processes that are currently blocked

This metric is only available when the receiver is configured to directly connect to SQL Server.

| Unit | Metric Type | Value Type |
| ---- | ----------- | ---------- |
| {processes} | Gauge | Int |

### sqlserver.replica.data.rate

Throughput rate of replica data.

| Unit | Metric Type | Value Type |
| ---- | ----------- | ---------- |
| By/s | Gauge | Double |

#### Attributes

| Name | Description | Values | Optional |
| ---- | ----------- | ------ | -------- |
| replica.direction | The direction of flow of bytes for replica. | Str: ``transmit``, ``receive`` | false |

### sqlserver.resource_pool.disk.operations

The rate of operations issued.

This metric is only available when the receiver is configured to directly connect to SQL Server.

| Unit | Metric Type | Value Type |
| ---- | ----------- | ---------- |
| {operations}/s | Gauge | Double |

#### Attributes

| Name | Description | Values | Optional |
| ---- | ----------- | ------ | -------- |
| direction | The direction of flow of bytes or operations. | Str: ``read``, ``write`` | false |

### sqlserver.resource_pool.disk.throttled.read.rate

The number of read operations that were throttled in the last second

This metric is only available when the receiver is configured to directly connect to SQL Server.

| Unit | Metric Type | Value Type |
| ---- | ----------- | ---------- |
| {reads}/s | Gauge | Int |

### sqlserver.resource_pool.disk.throttled.write.rate

The number of write operations that were throttled in the last second

This metric is only available when the receiver is configured to directly connect to SQL Server.

| Unit | Metric Type | Value Type |
| ---- | ----------- | ---------- |
| {writes}/s | Gauge | Double |

### sqlserver.table.count

The number of tables.

| Unit | Metric Type | Value Type | Aggregation Temporality | Monotonic |
| ---- | ----------- | ---------- | ----------------------- | --------- |
| “{tables}” | Sum | Int | Cumulative | false |

#### Attributes

| Name | Description | Values | Optional |
| ---- | ----------- | ------ | -------- |
| table.state | The state of the table. | Str: ``active``, ``inactive`` | false |
| table.status | The status of the table. | Str: ``temporary``, ``permanent`` | false |

### sqlserver.transaction.delay

Time consumed in transaction delays.

| Unit | Metric Type | Value Type | Aggregation Temporality | Monotonic |
| ---- | ----------- | ---------- | ----------------------- | --------- |
| ms | Sum | Double | Cumulative | false |

### sqlserver.transaction.mirror_write.rate

Total number of mirror write transactions.

| Unit | Metric Type | Value Type |
| ---- | ----------- | ---------- |
| “{transactions}/s” | Gauge | Double |

## Default Events

The following events are emitted by default. Each of them can be disabled by applying the following configuration:

```yaml
events:
  <event_name>:
    enabled: false
```

## Optional Events

The following events are not emitted by default. Each of them can be enabled by applying the following configuration:

```yaml
events:
  <event_name>:
    enabled: true
```

### db.server.query_sample

query sample

#### Attributes

| Name | Description | Values |
| ---- | ----------- | ------ |
| client.address | Hostname or address of the client. | Any Str |
| client.port | TCP port used by the client. | Any Int |
| db.namespace | The database name. | Any Str |
| db.query.text | The text of the database query being executed. | Any Str |
| db.system.name | The database management system (DBMS) product as identified by the client instrumentation. | Any Str |
| network.peer.address | IP address of the peer client. | Any Str |
| network.peer.port | TCP port used by the peer client. | Any Int |
| sqlserver.blocking_session_id | Session ID that is blocking the current session. 0 if none. | Any Int |
| sqlserver.context_info | Context information for the session, represented as a hexadecimal string. | Any Str |
| sqlserver.command | SQL command type being executed. | Any Str |
| sqlserver.cpu_time | CPU time consumed by the query, in seconds. | Any Double |
| sqlserver.deadlock_priority | Deadlock priority value for the session. | Any Int |
| sqlserver.estimated_completion_time | Estimated time remaining for the request to complete, in seconds. | Any Double |
| sqlserver.lock_timeout | Lock timeout value in seconds. | Any Double |
| sqlserver.logical_reads | Number of logical reads (data read from cache/memory). | Any Int |
| sqlserver.open_transaction_count | Number of transactions currently open in the session. | Any Int |
| sqlserver.percent_complete | Percentage of work completed. | Any Double |
| sqlserver.query_hash | Binary hash value calculated on the query and used to identify queries with similar logic, reported in the HEX format. | Any Str |
| sqlserver.query_plan_hash | Binary hash value calculated on the query execution plan and used to identify similar query execution plans, reported in the HEX format. | Any Str |
| sqlserver.query_start | Timestamp of when the SQL query started (ISO 8601 format). | Any Str |
| sqlserver.reads | Number of physical reads performed by the query. | Any Int |
| sqlserver.request_status | Status of the request (e.g., running, suspended). | Any Str |
| sqlserver.row_count | Number of rows affected or returned by the query. | Any Int |
| sqlserver.session_id | ID of the SQL Server session. | Any Int |
| sqlserver.session_status | Status of the session (e.g., running, sleeping). | Any Str |
| sqlserver.total_elapsed_time | Total elapsed time for completed executions of this plan, reported in delta seconds. | Any Double |
| sqlserver.transaction_id | Unique ID of the active transaction. | Any Int |
| sqlserver.transaction_isolation_level | Transaction isolation level used in the session. Represented as numeric constant. | Any Int |
| sqlserver.wait_resource | The resource for which the session is waiting. | Any Str |
| sqlserver.wait_time | Duration in seconds the request has been waiting. | Any Double |
| sqlserver.wait_type | Type of wait encountered by the request. Empty if none. | Any Str |
| sqlserver.writes | Number of writes performed by the query. | Any Int |
| user.name | Login name associated with the SQL Server session. | Any Str |

### db.server.top_query

top query

#### Attributes

| Name | Description | Values |
| ---- | ----------- | ------ |
| sqlserver.total_worker_time | Total amount of CPU time that was consumed by executions of this plan since it was compiled, reported in delta seconds. | Any Double |
| db.query.text | The text of the database query being executed. | Any Str |
| sqlserver.execution_count | Number of times that the plan has been executed since it was last compiled, reported in delta value. | Any Int |
| sqlserver.total_logical_reads | Total number of logical reads performed by executions of this plan since it was compiled, reported in delta value. | Any Int |
| sqlserver.total_logical_writes | Total number of logical writes performed by executions of this plan since it was compiled, reported in delta value. | Any Int |
| sqlserver.total_physical_reads | Total number of physical reads performed by executions of this plan since it was compiled, reported in delta value. | Any Int |
| sqlserver.query_hash | Binary hash value calculated on the query and used to identify queries with similar logic, reported in the HEX format. | Any Str |
| sqlserver.query_plan | The query execution plan used by the SQL Server. | Any Str |
| sqlserver.query_plan_hash | Binary hash value calculated on the query execution plan and used to identify similar query execution plans, reported in the HEX format. | Any Str |
| sqlserver.total_rows | Total number of rows returned by the query, reported in delta value. | Any Int |
| sqlserver.total_elapsed_time | Total elapsed time for completed executions of this plan, reported in delta seconds. | Any Double |
| sqlserver.total_grant_kb | The total amount of reserved memory grant in KB this plan received since it was compiled, reported in delta value. | Any Int |
| server.address | The network address of the server hosting the database. | Any Str |
| server.port | The port number on which the server is listening. | Any Int |
| db.system.name | The database management system (DBMS) product as identified by the client instrumentation. | Any Str |

## Resource Attributes

| Name | Description | Values | Enabled |
| ---- | ----------- | ------ | ------- |
| host.name | The host name of SQL Server | Any Str | true |
| server.address | Name of the database host. | Any Str | false |
| server.port | Server port number. | Any Int | false |
| sqlserver.computer.name | The name of the SQL Server instance being monitored. | Any Str | false |
| sqlserver.database.name | The name of the SQL Server database. | Any Str | true |
| sqlserver.instance.name | The name of the SQL Server instance being monitored. | Any Str | false |
