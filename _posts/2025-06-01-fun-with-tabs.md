---
layout: post
title: Sploosh! Adventures in Auto-Completion
date: 2025-06-01 09:10
category: 
author: Adam Adair
tags: [Sploosh POSIX Shell]
summary: 
---

# Adventures in Auto-Completion: Tab-tastic Times with Sploosh!

There’s something magical about hitting the `Tab` key and watching your terminal finish your thoughts like a caffeinated psychic. I knew I wanted *Sploosh!* (The Shell) to have that magic. What I didn’t expect was the chaos, heartbreak, and weirdly satisfying triumph that would come from trying to make it happen.

At first, I was naive. I thought, “Hey, how hard could it be? The user presses tab, we finish the word. Boom. Easy.” Reader, it was not easy.

I began with NCmd. I had previously tackled a similar problem when I created a library named NCmd for creating command line programs. It had a form of tab initiated auto-completions, so I copied that code into Sploosh! I loaded it up with the builtin commands and it worked beautifully on my machine. So I sent it to the tester.

**FAIL.**

Nothing was showing up in the automated testing. Nothing but the '$' prompt no matter what kind of keystrokes were sent to the program. This form of blackbox testing makes it difficult to know where to start debugging. I discussed things with ChatGPT to get some ideas, and one of the recommendations was to use the library [ReadLine](https://github.com/tonerdo/readline).

I liked ReadLine. ReadLine was kind to me… at first. I wired up some completions, smiled at how nicely they showed up in the terminal, and then proudly ran the solution through the automated tests.

**FAIL AGAIN!!**

Apparently, what I saw and what the tester saw were two entirely different realities. On my end, I had beautiful completions sparkling like digital confetti. On their end? Nothing. Nada. It was like we were performing a magic trick behind a brick wall.

So naturally, I did what any self-respecting dev does when faced with an invisible magic trick: I tore apart the source code and started hacking.

Some highlights of this journey:
- Discovered the tab handler was cycling through completions like a carousel on fast-forward.
- Watched in horror as it "helpfully" erased our tokens with surgical precision, replacing them with its own questionable decisions.
- Laughed (and maybe cried) while rewriting core behavior because the original code was just too fancy for our humble test runner to comprehend.

I eventually got it working. I ditched completion cycling, rewrote how suggestions printed, and made the experience a lot more bash-like. And yes, it passed the tests. It even *felt* right.

The best part? Despite the frustration, I genuinely had fun. There’s something deeply satisfying about bending a library to your will, even if it means yelling at your monitor for a few hours first.

Next up: maybe we teach it how to read your mind when you forget the name of that one script you wrote six weeks ago? Or maybe we’ll just settle for handling redirection without setting our keyboard on fire.

Until next time, keep tabbing!

