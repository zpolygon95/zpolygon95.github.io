---
layout: post
title: "New Projects Page"
date: 2018-12-05 08:23:00 -0500
categories: blog meta
---
It would have been simple just to redirect to my github page, and use the pinned
repositories feature as my effective "Projects Page", but I was in the mood to
make something!

I found myself manually writing tables into a static project page, and I thought

> Wait a second, I'm a programmer!

and started reading about the google sheets API. Unfortunately, I couldn't find
any way in the API to anonymously access a published document -- so I went with
the next best: fetching the published document as a CSV.

Having spent so much time with really low level languages, I have a deep
appreciation for modern languages with good string manipulation features. I
typically hold python up as the platonic ideal, but vanilla javascript was just
as easy in this case. Of course, parsing CSVs isn't all that difficult, but it's
easy to take `string.split(",")` for granted.

So the end result is that I get to manage my list of projects in a google
spreadsheet, and the data will automatically be displayed on the projects page
using the correct look-and-feel for the current theme.

One thing I appreciate about the minima theme is that the links in the header
are editable just by adding markdown to the site root, so I don't need to extend
the theme just to add a link! As a result, the [projects][1] page can be
found in the header ([or here, if you prefer][1]).

[1]: https:zjp.io/projects/
