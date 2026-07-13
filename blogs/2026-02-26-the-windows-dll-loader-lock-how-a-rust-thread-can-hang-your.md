---
title: "The Windows DLL loader lock: how a Rust thread can hang your JVM"
url: "https://questdb.com/blog/windows-dll-loader-lock-rust-jni-deadlock/"
date: "2026-02-26"
author: ""
feed_url: "https://questdb.com/rss.xml"
---
Debugging sporadic Windows CI hangs through process dumps and WinDbg, uncovering a DLL loader-lock deadlock between Rust thread teardown and JVM safepoints.
