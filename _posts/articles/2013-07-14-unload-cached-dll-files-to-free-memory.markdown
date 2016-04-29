---
layout: post
category: article
title:  "Unload Cached Dll Files To Free Memory"
date: 2013-07-14 13:57:25 +0530
meta: "Unload Cached Dll Files To Free Memory"
permalink: /article/unload-cached-dll-files-to-free-memory
author: Ajeet Prajapati
---
Windows Explorer caches DLLs (Dynamic-Link Libraries) in memory for a period of time after the application an using them has been closed. Which in some cases can be an waste of memory. To stop WinXP from always caching these DLL files, create the new registry key below.

Open up the Registry and navigate to:

```
HKEY_LOCAL_MACHINE\ SOFTWARE\ Microsoft\ Windows\ CurrentVersion\ Explorer
```

Create a new sub-key named 'AlwaysUnloadDLL' and set the default value to equal '1' to disable Windows caching the DLL in memory.

Restart Windows for the change to take effect.