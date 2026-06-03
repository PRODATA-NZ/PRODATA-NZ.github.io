---
title: "Successfully completed migration to PostgreSQL 17.2"
date: 2025-01-09 13:27:00 +0800
excerpt: "We completed testing and migration of all PRO DATA customer solutions to PostgreSQL 17."
categories:
  - db
  - postgres
  - postgresql
---
On September 26, 2024, the PostgreSQL Global Development Group announced the release of PostgreSQL 17, the latest version of the world's most advanced open-source database. We are excited to share the successful completion of testing and the migration of all solutions provided by PRO DATA to PostgreSQL 17 for our valued customers.

PostgreSQL 17 builds on decades of open-source development, enhancing its performance and scalability while adapting to emerging data access and storage patterns. This release includes significant performance improvements, such as an overhauled memory management implementation for vacuum processes, optimizations for storage access, and enhancements for high-concurrency workloads. Additionally, there are speed-ups in bulk loading and exports, as well as improvements in query execution for indexes.

New features in PostgreSQL 17 benefit both new workloads and critical systems. The developer experience has been enhanced with the introduction of the SQL/JSON `JSON_TABLE` command, and improvements have been made to logical replication, simplifying the management of high-availability workloads and major version upgrades.

PostgreSQL 17 exemplifies the contributions of the global open-source community that drives its development, delivering enhancements that support users at all stages of their database journey. Whether you are managing databases at scale or seeking new features that enhance the developer experience, PostgreSQL 17 will improve your data management capabilities.

With over 25 years of open-source development from a worldwide developer community, PostgreSQL and the solutions developed and supported by PRO DATA—renowned for their reliability, robustness, and extensibility—have become the preferred open-source relational database for organizations of all sizes.

# System-wide performance gains

The vacuum process in PostgreSQL is essential for maintaining healthy operations, as it requires server resources to function effectively. PostgreSQL 17 introduces a new internal memory structure for vacuuming that consumes up to 20 times less memory. This enhancement improves vacuum speed and reduces the use of shared resources, allowing more resources to be available for your workload.

PostgreSQL 17 continues to enhance the performance of its I/O layer. High-concurrency workloads may experience up to twice the write throughput due to improvements in write-ahead log (WAL) processing. Additionally, the new streaming I/O interface accelerates sequential scans (which read all the data from a table) and speeds up how quickly the ANALYZE command can update planner statistics.

This version also extends performance gains to query execution. PostgreSQL 17 improves the performance of queries with IN clauses that utilize B-tree indexes, the default indexing method in PostgreSQL. Moreover, BRIN indexes now support parallel builds. The release includes several enhancements for query planning, such as optimizations for NOT NULL constraints and improvements in processing common table expressions (WITH queries). Additionally, this version adds more SIMD (Single Instruction/Multiple Data) support for accelerating computations, including the use of AVX-512 for the bit_count function.

# Further expansion of a robust developer experience

PostgreSQL was the first relational database to introduce JSON support in 2012, and with the release of PostgreSQL 17, its implementation of the SQL/JSON standard has been further enhanced. A notable feature in this version is JSON_TABLE, which allows developers to convert JSON data into a standard PostgreSQL table. PostgreSQL 17 also supports SQL/JSON constructors such as JSON, JSON_SCALAR, and JSON_SERIALIZE, along with query functions like JSON_EXISTS, JSON_QUERY, and JSON_VALUE. These additions provide developers with various methods to interact with JSON data. Moreover, this release introduces more jsonpath expressions focused on transforming JSON data into native PostgreSQL data types, including numeric, boolean, string, and date/time types.

In addition to JSON enhancements, PostgreSQL 17 expands the capabilities of the MERGE statement, which is used for conditional updates. This includes the addition of a RETURNING clause and the ability to perform updates on views. The release also improves bulk loading and data export functionalities, featuring up to a 2x performance improvement when exporting large rows with the COPY command. Furthermore, performance improvements are observed when the source and destination encodings match. A new option, ON_ERROR, has been introduced, allowing an import to continue even if an insert error occurs.

PostgreSQL 17 enhances features for managing data within partitions and across remote PostgreSQL instances. It now supports identity columns and exclusion constraints on partitioned tables. Additionally, the PostgreSQL foreign data wrapper (postgres_fdw), which is used for executing queries on remote PostgreSQL instances, now allows the pushing of EXISTS and IN subqueries to the remote server, enabling more efficient processing.

Lastly, PostgreSQL 17 includes a built-in, platform-independent, immutable collation provider. This provider is guaranteed to be immutable and offers sorting semantics similar to the C collation, utilizing UTF-8 encoding instead of SQL_ASCII. With this new collation provider, you can be assured that your text-based queries will return consistent sorted results, regardless of where PostgreSQL is executed.

# Logical replication enhancements for high availability and major version upgrades

Logical replication is used to stream data in real-time across various use cases. Previously, users who wanted to perform a major version upgrade had to drop logical replication slots, which meant resynchronizing data to subscribers after the upgrade. However, starting with upgrades from PostgreSQL 17, users no longer need to drop logical replication slots, simplifying the upgrade process when using logical replication.

PostgreSQL 17 also introduces failover control for logical replication, enhancing its resilience in high-availability environments. Additionally, it now includes the `pg_createsubscriber` command-line tool, which allows users to convert a physical replica into a new logical replica.

# More options for managing security and operations

PostgreSQL 17 has introduced new features to enhance the management of database system lifecycles. One significant update is the new TLS option, `ssl-negotiation`, which allows users to perform direct TLS handshakes when using ALPN (Application-Layer Protocol Negotiation), registered as PostgreSQL in the ALPN directory. Additionally, PostgreSQL 17 adds the predefined role `pg_maintain`, granting users permission to carry out maintenance operations.

The backup utility, `pg_basebackup`, now supports incremental backups and introduces the `pg_combinebackup` utility, which enables users to reconstruct a full backup. Moreover, the `pg_dump` utility has a new option, `--filter`, that allows users to specify which objects to include when generating a dump file.

Enhancements to monitoring and analysis features have also been made in PostgreSQL 17. The `EXPLAIN` command now shows the time spent on local I/O block reads and writes and adds two new options: `SERIALIZE` and `MEMORY`. These options help users understand the time spent on data conversion for network transmission and the memory used. Additionally, PostgreSQL 17 reports the progress of vacuuming indexes and introduces the `pg_wait_events` system view, which, when used alongside `pg_stat_activity`, provides greater insight into the reasons an active session is waiting.

# About PostgreSQL

PostgreSQL is the world's leading open-source database, backed by a thriving global community of thousands of users, contributors, companies, and organizations. With over 35 years of engineering excellence that began at the University of California, Berkeley, PostgreSQL has consistently set the standard for development speed and innovation. Its robust feature set not only rivals top proprietary database systems but decisively outperforms them in advanced capabilities, extensibility, security, and stability.
