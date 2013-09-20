---
layout: post
title:  "Loop through Gridview’s data keys"
tags: programming asp.net c#
---

Today I was working with a GridView that has the ability to export to Excel. I wanted to mark all exported rows in the database. 

After far more searching than should have been necessary, I came up with the following solution:

    foreach (DataKey dataKey in myGridView.DataKeys)
    {
        MarkRecordAsExported(dataKey.Value.ToString);
    }

I thought I would need LINQ and casting and such…turns out you can just loop through the GridView’s data keys.
