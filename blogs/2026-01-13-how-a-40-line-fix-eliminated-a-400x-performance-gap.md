---
title: "How a 40-Line Fix Eliminated a 400x Performance Gap"
url: "https://questdb.com/blog/jvm-current-thread-user-time/"
date: "2026-01-13"
author: "Jaromir Hamala"
feed_url: "https://questdb.com/rss.xml"
---
How a 40-line OpenJDK fix swapped slow /proc parsing for a single clock_gettime syscall, closing a 400x thread CPU-time gap hidden for 20 years.
