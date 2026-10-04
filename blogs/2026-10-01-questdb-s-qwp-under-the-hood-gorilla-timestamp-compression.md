---
title: "QuestDB's QWP under the hood: Gorilla timestamp compression"
url: "https://questdb.com/blog/questdb-qwp-gorilla-timestamp-compression/"
date: "2026-10-01"
author: "Javier Ramirez"
feed_url: "https://questdb.com/rss.xml"
---
How QWP, QuestDB's binary wire protocol, uses Gorilla delta-of-delta encoding to send a timestamp in as little as one bit, worked through on real ticks.
