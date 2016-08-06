---
layout: post
title: "Number or String?"
tags: database
---
If a value contains only numeric digits, when should you store it as a number in the database, and when as a string?

<img alt="Flowchart for when to store value as number or string in the database." src="/images/number-vs-string.png">

- Phone numbers, US ZIP codes, and credit card numbers can start with a zero: store them as strings.
- Product prices can be added (multiple products), subtracted and divided (coupons): store them as numbers.
- Store as number any sortable report column values. Otherwise you’ll get “1, 10, 2” instead of “1, 2, 10”.
- This one is debatable: if you are storing e.g. a US ZIP code, and you are validating that it only contains numeric digits, should you store it as a number even though you don’t need arithmetic done? I would probably still store it as a string, but I wouldn’t argue if you make it a number.