---
layout: post
title: Sploosh! Refactoring stuff
date: 2025-06-05 17:10
category: 
author: Adam Adair
tags: [Sploosh POSIX Shell]
summary: 
---

# Breaking Up Is Hard to Do (Unless You're a Built-in Command)
I was starting to notice a problem with the code.

## The Problem: A Dysfunctional Relationship

Once upon a time in the land of `Sploosh!`, all of our built-in commands lived under one roof — the `CommandManager` class. It was a crowded place. You had `cd` brooding in one corner, `exit` trying to ghost everyone, and `echo` shouting over everyone just to feel heard.

The result? Spaghetti logic, testability tantrums, and a whole lot of tight coupling that made adding a new command feel like defusing a bomb using only chopsticks.

## The Solution: Interface Intervention

It was time for a change. An intervention. A **design pattern** kind of intervention.

So we broke them up. Gave each command their own space to grow. Now they implement the beautiful, minimalist `IBuiltInCommand` interface:

```csharp
public interface IBuiltInCommand
{
    string Name { get; }
    bool Execute(ParsedCommand cmd);
    string HelpText { get; }
}
```

No more shouting over each other. No more shared fridge of despair. Just clean, isolated behavior in individual classes.

## Why This Rocks

- **Encapsulation**: `cd` doesn't have to worry about `pwd`'s messy side effects.
- **Testability**: We can now interrogate `exit` without it storming out of the room.
- **Extensibility**: Want to add `clear`? Just drop in a new class and implement the interface.
- **Readability**: Navigating the code no longer requires spelunking gear.

## A Brief (and Weird) History of Built-in Commands

Built-in shell commands in UNIX date all the way back to the **Seventies**. Back then, resources were limited, so certain commands like `cd`, `exit`, and `echo` were implemented *inside the shell* itself to avoid the cost of forking a new process. Efficiency wasn't just a goal — it was a survival mechanism.

And then there's **`echo`**. Oh, `echo`.

Depending on your shell, `echo` might:
- Honor backslash escapes (`\n`, `\t`)
- *Not* honor them
- Interpret `-n` as "no newline"
- Or interpret `-n` as just more text to echo

Fun fact: POSIX *almost* banned `echo` in favor of `printf`, which is more consistent across shells. But `echo` survived, like a cockroach of the UNIX command line.

And now, in `Sploosh!`, it's got its own classy class. 🫡

## The Future

We’ve laid the groundwork for a brighter, cleaner, more modular future. Each built-in command now walks tall with its own purpose, and the shell is all the better for it.

Will we ever forgive the sins of `CommandManager` past? Maybe not. But we’ve moved on. With dignity. And an interface we’re proud of.

**Long live modularity. Long live `IBuiltInCommand`.**

— _The Sploosh! Dev Team (a.k.a. Me)_
