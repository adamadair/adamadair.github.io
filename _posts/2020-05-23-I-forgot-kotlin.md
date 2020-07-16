---
layout: post
title: I forgot Kotlin
date: 2020-05-23 12:41
category: 
author: Adam Adair 
tags: []
summary: Creating Dates and stuff in Kotlin
---

> "A goal without a plan is just a wish." -Antoine de Saint-Exupéry

I have haven't written a line of Kotlin since last December so when I started a new personal Android based project this morning
I did not expect for things to go as slow as they did. I really forgot quite a bit in the last 5 months and that disturbs me a little. Either I didn't really know Kotlin as well as I thought, or I've entered the part of my life where I start to forget everything. I'm actually hoping for the first option. 

# Kotlin Dates
In my project I need to do some date based operations like sorting items based on completion date, or displaying a list of items filtered by month. This requires using Java's Date class, and I would love to insert a long rant at how poor Java's related Date classes are compared to other modern languages, but that is not the goal of post. I simply want to get a date object from a string in the format 'yyyy-mm-dd'.

