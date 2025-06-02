---
layout: post
title: Sploosh! Pipes, Pain, and the Surprisingly Pleasant Past
date: 2025-06-02 17:10
category: 
author: Adam Adair
tags: [Sploosh POSIX Shell]
summary: 
---

# 🛠️ *SPLOOSH!* Blog Post #3  
## “Pipes, Pain, and the Surprisingly Pleasant Past”

This week, *SPLOOSH!* graduated from “barely a pipe dream” to “fully piped up and passing tests.” That’s right: pipelines are in, and they actually work. Multiple commands, redirections, built-ins, the whole glorious mess—you name it, I piped it.  

Was it smooth? No.  
Was it fun? Also no.  
Did it work eventually? Absolutely.  

There was a particularly dark day when I stared into the abyss of `ExecutePipelineWithNoBuiltins` and it stared right back, whispering *“deadlock…”*. Turns out that launching processes in the wrong order is like trying to pass the baton in a relay race by throwing it backwards into a wind tunnel. Lesson learned.

But just as I crawled out of the trench with mud in my hair and `MemoryStreams` in my teeth, I turned to the **history** feature—and it was like flipping on easy mode.

Implementing command history was a breath of fresh air:
- Arrow key navigation? ✔️  
- Typing `history` to see my past mistakes? ✔️  
- Repeating said mistakes with a single keypress? ✔️  

It worked *the first time*. Which is suspicious, and probably means there’s a cursed `while (true)` loop hidden somewhere, but I’m not going to look at it. Not today.

So now, *SPLOOSH!* is no longer just a shell. It remembers.  
It evolves.  
It even passes tests.

Stay tuned for my next adventure: either job control, signal handling… or something weird like scripting support, depending on how much coffee I drink.
