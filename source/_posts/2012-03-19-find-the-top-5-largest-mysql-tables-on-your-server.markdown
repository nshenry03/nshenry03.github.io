---
layout: post
title: "Find the top 5 largest MySQL tables on your server"
date: 2012-03-19 19:39:17 -0700
comments: true
categories: 
- mysql
---

```sql
SELECT
  CONCAT(table_schema, '.', table_name) AS tableName,
  CONCAT(ROUND(table_rows / 1000, 2), ' Thousand') AS numberOfRows,
  CONCAT(ROUND(data_length / ( 1024 * 1024 ), 2), ' MB') AS dataSize,
  CONCAT(ROUND(index_length / ( 1024 * 1024 ), 2), ' MB') AS indexSize,
  CONCAT(ROUND(( data_length + index_length ) / ( 1024 * 1024 ), 2), ' MB') AS totalSize,
  ROUND(index_length / data_length, 2) AS indexFraction
FROM information_schema.TABLES
ORDER  BY data_length + index_length DESC
LIMIT  5;
```

<!-- more -->

    mysql> SELECT
        ->   CONCAT(table_schema, '.', table_name) AS tableName,
        ->   CONCAT(ROUND(table_rows / 1000, 2), ' Thousand') AS numberOfRows,
        ->   CONCAT(ROUND(data_length / ( 1024 * 1024 ), 2), ' MB') AS dataSize,
        ->   CONCAT(ROUND(index_length / ( 1024 * 1024 ), 2), ' MB') AS indexSize,
        ->   CONCAT(ROUND(( data_length + index_length ) / ( 1024 * 1024 ), 2), ' MB') AS totalSize,
        ->   ROUND(index_length / data_length, 2) AS indexFraction
        -> FROM information_schema.TABLES
        -> ORDER  BY data_length + index_length DESC
        -> LIMIT  5;
    +--------------------------+---------------+----------+-----------+-----------+---------------+
    | tableName                | numberOfRows  | dataSize | indexSize | totalSize | indexFraction |
    +--------------------------+---------------+----------+-----------+-----------+---------------+
    | drupal_10565.cache_menu  | 4.06 Thousand | 2.52 MB  | 0.11 MB   | 2.63 MB   |          0.04 |
    | mysql.help_topic         | 0.51 Thousand | 0.42 MB  | 0.02 MB   | 0.44 MB   |          0.05 |
    | drupal_10565.menu_router | 0.42 Thousand | 0.19 MB  | 0.14 MB   | 0.33 MB   |          0.75 |
    | drupal_10565.cache       | 0.01 Thousand | 0.27 MB  | 0.02 MB   | 0.28 MB   |          0.06 |
    | drupal_10565.watchdog    | 0.75 Thousand | 0.20 MB  | 0.06 MB   | 0.27 MB   |          0.31 |
    +--------------------------+---------------+----------+-----------+-----------+---------------+
    5 rows in set (0.07 sec)
