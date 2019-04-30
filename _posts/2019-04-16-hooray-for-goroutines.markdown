---
layout: post
title: "Hooray for Goroutines!"
date: "2019-04-16 13:09:57 -0500"
---
This post is more to test whether I high highlight source code for Go or not.
I've really been enjoying learning and programming in Go recently. As I had
mentioned in a previous Post I had worked through the ["The Go Programming Language"](https://www.amazon.com/Programming-Language-Addison-Wesley-Professional-Computing/dp/0134190440/ref=sr_1_3?crid=2TRV1XULDBCJ3&keywords=go+programming+language&qid=1555438884&s=gateway&sprefix=Go+programming%2Caps%2C155&sr=8-3)
book, and Chapter 8 is about Goroutines and Channels. I have to admit that I
didn't "get it" at first, just like get OOP right away and its not until you
solve your first problem on your own using a language feature that triggers
that "Ah Ha!" moment.

## The Problem
We're given 2 huge integers represented by linked lists. Each linked list element
is a number from `0` to `9999` that represents a number with exactly `4` digits.
The represented number might have leading zeros. The task is to add up these
huge integers and return the result in the same format.

The definition for the singly linked list is:

{% highlight go %}
type ListNode struct {
   Value interface{}
   Next *ListNode
}

{% endhighlight %}

## Examples

# Stop the Presses

So I was originally going to show an average solution to the problem, and then
I was going to show how much more clever my solution was using Goroutines
and how much shorter it ended up being than most peoples.

I was going to that...and then I saw a solution written in C++ that was shorter than my solution,
used no recursion and solved it in O(N) time and it was so beautiful I
nearly wept.

I was then disgusted with my own solution. I was so shaken with how poor my
own solution was compared to that work of art that I stopped blogging
for two weeks. I'm not a Go expert, but this really isn't about Go. It's about
being a good programmer and I really don't know where I stand when
compared to my peers of similar programming experience. Am I a good programmer,
am I an average programmer, or am I really poor at this?

If I'm trying to be honest, I believe I'm in the above average category. This is
what I love to do, and I do it professionally, but I am not exceptional at it.
