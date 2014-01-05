---
layout: post
title:  "Preventing Duplicate Selections with C# and jQuery Validation"
tags: asp.net c#
---

A few days ago, while working on a web page, I got to write my favorite type of code: validation.

![jQuery validation](/images/validation.png)

Ha ha. Actually I’d rather floss with a brick than write validation.

Anyway, I was writing validation for an ASP.NET/C# registration page. The page has three dropdown lists, each with the same list of courses. Students can register for up to three courses by choosing a course in each dropdown list. The validation I was writing needed to prevent a student from registering for a course multiple times. It seemed like there should be a simple solution, but it wasn’t jumping out at me, so I started to pseudocode a naive solution.

{% gist 8260138 PreventingDuplicates1.txt %}

Okay, not very elegant. And not easily scalable <del>if</del> when I’m asked to add a fourth dropdown.
I started coding it out a little more in the hopes of seeing a pattern.

{% gist 8260138 PreventingDuplicates2.txt %}

Then I had a “eureka” moment: I could put the values in an array, get the count of unique items, and check if the number of values is equal to the number of unique values.

{% gist 8260138 PreventingDuplicates1.cs %}

This works because I don’t care how many duplicates there are, or which values are duplicated. I just want to know if duplicates exist.

However, it’s not quite complete. If a student registers for only one course, say “History 101”, dropdown list 1 will have the value “HI 101” and dropdowns 2 and 3 will be empty strings. Since ```"" == ""```, I’ll need to allow multiple empty strings.

{% gist 8260138 PreventingDuplicates2.cs %}

Boom. And in jQuery:

{% gist 8260138 PreventingDuplicates.js %}

I still don’t like writing validation, but…it has its interesting moments.