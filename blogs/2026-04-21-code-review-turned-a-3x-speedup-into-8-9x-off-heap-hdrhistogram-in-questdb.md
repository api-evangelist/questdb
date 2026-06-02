---
title: Code review turned a 3x speedup into 8.9x (off-heap HdrHistogram in QuestDB)
url: https://questdb.com/blog/code-review-tripled-histogram-speedup/
date: '2026-04-21'
author: Javier Ramirez
feed_url: https://questdb.com/rss.xml
---
A community contribution ports HdrHistogram to off-heap memory for QuestDB's approx_percentile() function. The first benchmark is promising in parallel but regresses single-threaded. After a collaborative review, the regression is gone and the parallel speedup reaches 8.9x. Here is what changed.
