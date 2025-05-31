---
layout: post
title: Introducing Sploosh!
date: 2025-05-31 16:35
category: 
author: Adam Adair
tags: []
summary: 
---

# 🐚 Introducing Sploosh! – A C# Shell Project

Ever thought to yourself, *“You know what my Linux box needs? A shell written in C#”*?

Me neither — until I did.

Welcome to **Sploosh!**, my somewhat serious, occasionally snarky journey into building a **POSIX-compliant shell** using **C#** on Linux. This blog series will chronicle the development of this project: from hacky beginnings to a (hopefully) usable command-line environment.

## Why Build a Shell in C#?

I’ve spent most of my professional life knee-deep in .NET — writing enterprise apps, consuming APIs, swearing at WCF, and generally getting stuff done in C#. But every so often, I like to step outside the usual day-job code and work on something... weirder.

Enter: Sploosh!

This started as a **side project for fun**, but quickly turned into a great **exercise in systems thinking**, **interprocess communication**, and **how far you can push C# in a traditionally UNIX-y domain**.

Plus, writing a shell forces you to think deeply about:
- Process management
- Redirection (`>`, `>>`, `<`, `2>`, etc.)
- Command parsing
- Signals
- Built-in vs external commands
- POSIX behavior expectations

And that's just the first leg of the journey.

## What’s Done So Far

Right now, Sploosh! can:
- Start a REPL that parses and executes basic commands
- Handle built-in commands like `cd` and `exit`
- Execute external programs with arguments
- Perform rudimentary input/output redirection (`>`, `>>`, `<`, `2>`)
- Launch from the CLI using `dotnet run` (still working on standalone execution issues)

Most recently, I’ve been tackling **redirection**, making sure it works even with **built-in commands** — not just spawned processes. I'm also starting to design a **`Command` abstraction** to cleanly model the steps from token parsing to execution.

There's a lot more on the roadmap — piping, job control, background processes, command substitution, maybe even tab completion someday. But for now, it's one test case at a time.

## What’s Next?

Coming up:
- A formal `Command` class to unify command parsing and execution
- More robust error handling
- Test suite integration that actually works *outside* of the CodeCrafters platform
- Eventually, building something worthy of daily driver status (or at least not crashing every 5 minutes)

This is as much a passion project as it is a learning tool. I’ll be using this blog to share code snippets, design thoughts, gotchas, and a few rants along the way.

So if you’ve ever wanted to see someone try to build a POSIX shell in a non-traditional language… buckle up.

**Sploosh!** is just getting started.
