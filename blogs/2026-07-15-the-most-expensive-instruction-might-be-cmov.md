---
title: "The Most Expensive Instruction Might Be… cmov"
url: "https://questdb.com/blog/cmov-vs-branch-perf/"
date: "2026-07-15"
author: "Jaromir Hamala"
feed_url: "https://questdb.com/rss.xml"
---
A trip through HotSpot's C2 branch-to-cmov heuristic: it measures branch bias, not predictability, and in a tight loop that mismatch is worth up to 2.9x.
