---
title: 'The Windows DLL loader lock: how a Rust thread can hang your JVM'
url: https://questdb.com/blog/windows-dll-loader-lock-rust-jni-deadlock/
date: '2026-02-26'
author: undefined
feed_url: https://questdb.com/rss.xml
---
A deep dive into debugging sporadic CI hangs on Windows, leading us through process dumps, WinDbg, and finally uncovering a deadlock between Rust thread destruction and the JVM's safepoint mechanism.
