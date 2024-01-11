---
title: "BAMandDAM"
layout: post
permalink: /bam-and-dam
categories: Application-Execution
---
## Location and Format

The Windows Background/Desktop Activity Monitor (BAM/DAM) are located in two SYSTEM registry keys **"SYSTEM\CurrentControlSet\Services\bam\state\UserSettings\<SID>"** and **"SYSTEM\CurrentControlSet\Services\dam\state\UserSettings\<SID>"** respectively.

## Purpose

The goal of the Amcache.hve is to track the status of installed applications, programs executed, and drivers that are loaded. This is one of the few forensic artifacts that tracks the SHA1 hash of the executable driver. This feature is a great benefit to Forensicators, most artifcats require us to rely on file name alone.

## Forensic Uses

One of the main benefits of this artifact is the SHA1 hash that was previously mentioned. However, another overlooked feature is its format as a registry hive. Along with the file hash, we are also given:
- Full path, file size, and file modification time
- Publisher metadata information
- Executable compilation time
It is important to note that **an executable's presence in the amcache.hve does not indicate execution.** Instead it should be viewed as an indication that the executable was present on the system but not necessarily executed.

## Example Analysis

pending