---
layout: post
title:  "Oracle Parameter Precision"
tags: programming oracle pl/sql
---

When I first started writing Oracle PL/SQL, I tried to define function and procedure parameters in the same way I defined SQL table columns:

{% gist 8260111 PLSQLDeclaration1.sql %}

Of course, you get a compile-time error if you try to specify precision for parameters. Instead you have to do:

{% gist 8260111 PLSQLDeclaration2.sql %}

Ah, but you can also define parameter types in terms of tables:

{% gist 8260111 PLSQLDeclaration3.sql %}

And I assumed this enforced the precision of the table’s columns, if it had any. 

Never assume.

The parameters will not enforce the precision of the columns they are based on. 

Why doesn’t Oracle allow you to specify precision for your parameters? I assume (ha ha) that there’s an actual reason, but I don’t know enough to guess what that reason might be. ∎