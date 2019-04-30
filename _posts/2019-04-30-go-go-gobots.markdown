---
layout: post
title: "Go Go GoBots!"
date: "2019-04-30 15:15:55 -0500"
---

[Riddles.io](https://www.riddles.io/) is codesports platform where you write bots in a language of your
choice to play games in one of their hosted competitions. I've written bots
that play Texas Hold'em poker, Ultimate Tic Tac Toe, and other games. I was
recently on vacation in Arizona where I wrote down some notes on making a
bot to compete in their [AI Block Battle](https://playground.riddles.io/competitions/ai-block-battle)
game, which is a Tetris like competition. When I got home I coded a
quick bot in C# to get the communications down and uploaded it to the site
and then promptly forgot about it.

This week I checked on the bot and it had gone up to #9 in the standings, which
surprised me. The only thing this bot does is clear lines, as fast as it can.
The idea behind the heuristic is to stay alive as long as possible. This would
be a good bot to test new versions of the bot against, but I did not think it
would be in the top 10.

I think Go is a programming language that would work well for this type of
competition. My original program did not search very deeply for best moves, but
there is more that could be done to find the best fit current pieces. I've also
been looking for a fun project to really get into the Go programming language,
so I decided to make AI Block Battle bot in Go.

The initial version of the bot will be a survivor bot just like the C# version,
with the purpose of verifying communication with the Riddles game engine. Once
this bot is working well enough there are some improvements that are
"low hanging fruit". For each round in the game the bot is provide with not only
the current piece that needs to be placed, but also the next piece that will
come on the next turn. The C# bot did not make use of this knowledge, and I
think in very few lines of code we can make the survivor bot survive a little
bit longer.
