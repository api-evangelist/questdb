---
title: How we made WINDOW JOIN parallel and vectorized
url: https://questdb.com/blog/window-join-parallel-vectorized/
date: '2026-05-12'
author: Andrey Pechkurov
feed_url: https://questdb.com/rss.xml
---
WINDOW JOIN is QuestDB's dedicated syntax for aggregating one table over a time window around each row of another. We parallelized it across page frames, used a low-cardinality join key to unlock a vectorized aggregation path, and benchmarked it against Timescale, DuckDB, and ClickHouse on a 50M x 150M row workload.
