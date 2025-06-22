---
layout: post
title: How I Print Labels Like It’s 2005
date: 2025-06-21 19:10
category: 
author: Adam Adair
tags: [Humor Zebra Labels ZPL]
summary: How I Print Labels Like It’s 2005
---
# How I Print Labels Like It’s 2005

Ah, 2005.

The year *Batman Begins* reminded us that Batman could, in fact, begin again. The year YouTube launched. The year Java applets still walked the earth, proudly signed with expired certificates and optimism.

And me? I was printing labels from a web browser like some kind of wizard.

Fast-forward to today, where browser security is tighter than my jeans after Thanksgiving, and every attempt to print directly from a web app ends with a CORS error and my tears in the system logs.

So I did what any reasonable software engineer with 25+ years of experience and mild trust issues would do:  
I started writing my own local printing bridge in Go.

## 🧻 The Problem

Web browsers—those once-innocent portals to dancing baby GIFs—now live in hardened bunkers.  
They will not, *cannot*, allow your JavaScript to say:

> “Hey, could you just send this raw ZPL directly to a thermal printer connected via USB?”  

That’s not a request. That’s a felony.

## 🦾 What We Used to Do

In 2005, if I needed to print labels from a browser:

- I’d write a signed Java applet.
- Prompt the user to allow it access to their printer.
- Cross my fingers.
- Pray to the Sun Microsystems gods.

And you know what? It worked. On Windows. On Linux. Even on the one weird guy’s Mac.

It was beautiful, unholy sorcery. But those days are gone. Java applets were taken out back behind the shed and quietly deprecated.

## 🪦 The Sad Attempts

I tried everything modern web tech had to offer:

- **WebUSB**: Only works if you sacrifice a goat and the user is running Chrome on a Tuesday.
- **Browser extensions**: “Just install this unsigned extension from GitHub. Trust me.”
- **Cloud print services**: Because who *doesn't* want their HIPAA-compliant labels routed through six microservices and a Canadian server farm?

Eventually, I had to admit: the browser was not going to help me. If I wanted a ZPL command to actually hit a printer, I needed to go *local*.

## 🧰 The “Modern” Solution

Enter: my Go-based local printing bridge.

This is a tiny background app that:

1. Listens on `localhost`.
2. Accepts raw ZPL over HTTP.
3. Shoots it directly to a Zebra printer via USB or network socket.
4. Refuses to complain, unlike every browser I’ve ever met.

It’s fast. It’s quiet. It feels like the desktop equivalent of doing something behind your teacher’s back in high school.

I briefly considered writing it in C#—but that would require the .NET runtime, and I’m trying to keep client installs to a minimum. Also, Go builds one tidy binary and doesn’t care about your feelings.

## 🏷️ Why It Feels Like 2005 Again

- I’m printing directly to hardware without asking anyone’s permission.
- I’m ignoring modern security advice with confidence.
- I’m doing local installs that users don’t understand and can’t uninstall.
- I’m logging errors to the console like a savage.

It’s glorious.

## 💡 Closing Thoughts

If you, too, find yourself crying in front of your browser because you just want to print a damn label, consider going old-school. Build something local. Take control. Be the chaos.

Because sometimes the future isn’t browser-first.  
Sometimes, it’s just 2005 in disguise.
