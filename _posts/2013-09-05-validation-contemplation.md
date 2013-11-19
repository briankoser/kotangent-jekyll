---
layout: post
title:  "Validation Contemplation"
tags: asp.net c#
---

A few days ago, while working on a web page, I got to write my favorite type of code: validation.

![jQuery validation](/images/validation.png)

Ha ha. Actually I’d rather floss with a brick than write validation.

Anyway, I was writing validation for an ASP.NET/C# registration page. The page has three dropdown lists, each with the same list of courses. Students can register for up to three courses by choosing a course in each dropdown list. The validation I was writing needed to prevent a student from registering for a course multiple times. It seemed like there should be a simple solution, but it wasn’t jumping out at me, so I started to pseudocode a naive solution.

    valid if:
        1 != 2 and 
        2 != 3 and 
        3 != 1

Okay, not very elegant. And not easily scalable <del>if</del> when I’m asked to add a fourth dropdown.
I started coding it out a little more in the hopes of seeing a pattern.

    if 1 = "" && 2 = "" && 3 = ""
        valid
    if 1 != 2 && 1 != 3
        1 is valid

Then I had a “eureka” moment: I could put the values in an array, get the count of unique items, and check if the number of values is equal to the number of unique values.

    var courses = new[] { ddlCourse1.SelectedValue, ddlCourse2.SelectedValue, ddlCourse3.SelectedValue };
    e.IsValid = courses.Length != courses.Distinct().Count();

This works because I don’t care how many duplicates there are, or which values are duplicated. I just want to know if duplicates exist.

However, it’s not quite complete. If a student registers for only one course, say “History 101”, dropdown list 1 will have the value “HI 101” and dropdowns 2 and 3 will be empty strings. Since ```"" == ""```, I’ll need to allow multiple empty strings.

    IEnumerable courses = new [] { ddlCourse1.SelectedValue, ddlCourse2.SelectedValue, ddlCourse3.SelectedValue };
    courses = courses.Where(x => !String.IsNullOrEmpty(x));

    e.IsValid = courses.Count() == courses.Distinct().Count();

Boom. And in jQuery:

    var courses = $('.Course option:selected').map(function() { 
        if (this.value) {
            return this.value;
        }

        return null;
    });

    var uniqueCourses = $.grep(courses, function(value, index) {
        return $.inArray(value, courses) === index;
    });

    e.IsValid = courses.length === uniqueCourses.length;

I suppose even validation can be interesting.