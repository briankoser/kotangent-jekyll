---
layout: post
title:  "Loop through Gridview data keys"
tags: programming asp.net
---

Today I was adding an “Export to Excel” option to a Gridview. I wanted to mark each exported record in the database, but it wasn’t immediately apparent how I would do so. After far more searching than I expected, I came up with the following solution:

{% gist 8260040 %}

I was thinking I would need LINQ and casting and such…and it turns out you can just loop through a Gridview’s data keys. ∎