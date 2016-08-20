---
layout: post
title: "Code Smells"
tags: recommendation software
---
Great 10-year-old post on [code smells](https://blog.codinghorror.com/code-smells/) from the always-great Coding Horror by Jeff Atwood. Code smells are bad patterns that you should be on the look out for. I like to read through these every so often as a reminder. My favorite nuggets:

- Write code for people, not machines.
- Stamp out duplication whenever possible.
- Delete unused code (if you need it again, get it out of source control)
- If a change in one class requires cascading changes in several related classes, consider refactoring so that the changes are limited to a single class.