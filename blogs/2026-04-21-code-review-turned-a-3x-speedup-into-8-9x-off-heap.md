---
title: "Code review turned a 3x speedup into 8.9x (off-heap HdrHistogram in QuestDB)"
url: "https://questdb.com/blog/code-review-tripled-histogram-speedup/"
date: "2026-04-21"
author: ""
feed_url: "https://questdb.com/rss.xml"
---
A community PR ports HdrHistogram off-heap for QuestDB's approx_percentile(): fast in parallel but regressing single-threaded, until review reached 8.9x.
