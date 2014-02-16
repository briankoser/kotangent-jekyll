---
layout: post
title:  "12 Reasons I Hate SQL Developer"
tags: programming oracle
---

I don’t like SQL Developer. It’s hard to like a GUI with so many usability problems. The first version was released in 2006, but the interface feels much older. It’s certainly not bug-free, let alone polished. 

I’m told that it’s better than our office’s previous Oracle GUI (possibly Oracle Enterprise Manager?), and apparently Toad has it’s own problems. And hey, it’s free! At such times I imagine someone saying, “I know you don’t like getting punched in the gut, but it’s a lot better than back in the day when we got punched in the face. And hey, it’s a free punch in the gut!” 

OK, so I’m using hyperbole. A better analogy would be death by a thousand tiny cuts. Here is my personal list of the most annoying of the cuts, in no particular order.

##Tabs##
Attention makers of programs with tabs: all I want to do with tabs is move them left and right. I don’t want to pull them out and snap them inside the program window à la Windows 8. I don’t want them to float in front of the program window. And I certainly don’t want to only be able to move my tabs to the far right of the tab well, Oracle.

##Copy/paste##
Normally you can copy/paste a field from a table without problems. However, sometimes, for no apparent reason, instead of copying the contents of the field, the field will go into edit mode without placing the contents onto the clipboard.

##Collapsing procedures##
One of my favorite Visual Studio keyboard shortcuts  is <kbd>Ctrl</kbd> + <kbd>M</kbd>, <kbd>O</kbd>, which collapses methods so you can browse method definitions. SQL Developer kind of supports this; there’s no keyboard shortcut but you can right-click the gutter and select “Collapse procedure declarations/bodies”. Unfortunately, collapsed procedures will not stay collapsed for long; they’ll expand if you copy/paste into the package. Or if you expand other procedures nearby. Or sometimes if you just hit the return key. Or if it’s raining on a Tuesday.

##Search##
When I’m searching in a package header, I often want to search for the same thing in the package body. The search bar should do a global search, not just the current file.

##Undo function##
When you compile a package header, your undo history is deleted. Why does SQL Developer assume I would never want to undo code that I’ve just compiled?
Also, the undo history is very limited; I estimate the last 50 changes.

##<kbd>Ctrl</kbd> + click##
If you hold <kbd>Ctrl</kbd> and click on a function name in a package header, it will take you to the function body in the package body. Except when it doesn’t. There are some packages it just never works for. Sometimes it “works”; it takes me to the package body, but nowhere near the body of the function I clicked on. Even when working correctly, the navigated-to function is at the very bottom of the screen. Why can’t it be in the middle of the page, like when I search for the function name?

##Table scrolling GUI##
If you scroll through the contents of a table, switch tabs, then come back, you will be at the top of the results instead of where you had scrolled to.

##Error log window##
When you double-click on a package compilation error in the error log window, often it will bring up the line of code at the bottom of the worksheet…underneath the error log window. This is unavoidable if the code is on the last line of the package, but I’ve also noticed it for functions right in the middle of the file.

##Font Choice##
I like to be able to customize the font for programs, and in SQL Developer you can change the font used for the SQL editor and table data. I like to use a monospace font for code editing ([Source Code Pro](https://github.com/adobe/source-code-pro) is my current favorite.). However, when you edit data with the table GUI, SQL Developer always uses a proportional font. This is the opposite of font best practices: [editing text in a monospace font is much easier](http://www.joelonsoftware.com/uibook/chapters/fog0000000063.html). Proportional fonts are easier to read, so you would expect to find these used for display text, not for editing text.

##Table filter autocomplete##
If you start typing a column name into the table filter box and then accept the autocomplete, the column name will be put in place of what you have typed. Good. However, if you *finish* typing the name of the column and you accept the autocomplete (which still pops up even after you’ve typed a valid column), what you have typed will remain and the autocomplete will be tacked on to the end. Not good. For example, if I type “tableid = ” and the autocomplete offers “tableid = 123”, when I accept the autocomplete I end up with “tableid = tableid = 123”.

##Code templates##
Code templates are SQL Developer’s brand of text expansion. My main annoyance with them is that they don’t work in stored PL/SQL windows, only in worksheets. Since most of my time is spent in packages, I was never able to rely on this feature. However, this doesn’t really bother me anymore, because I now use [Breevy](http://www.16software.com/breevy/), which works everywhere. Highly recommended.

##Lack of column mode##
Nowadays I consider this a must-have text editor feature. Visual Studio and Notepad++ have a basic support of the feature, although neither compares to Sublime Text’s superb column mode. Even Geany has a column mode. Why doesn’t SQL Developer have column mode?

In the end, SQL Developer does the job, and perhaps these points are all quibbles. I still think that there’s no reason that a seven-year old program (albeit a free program) should have so many usability problems. ∎