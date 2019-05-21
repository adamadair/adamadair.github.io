---
layout: post
title: "Some thoughts about Tetris"
date: "2019-05-21 09:25:38 -0500"
---
Making an AI to play a game of Tetris competitively means having to watch it play many games to find out what is working and what is not working. I’ve watched more games of Tetris in the past week than I can count or remember, and not just my own bot’s games, but also the matches of the best bots to see how they approach the game. I’m not sure how many hours tetris I’ve watched, but it has to be more hours than the latest Avengers movie. I had a restless night of sleep last night in which my mind seemed to be showing endless games of Tetris on loop. I was not aware you could experience the Tetris Effect without actually playing the game directly.

I got my first GameBoy in a care package while I was in the Army and deployed to South West Asia back in 1991. My mother and my girlfriend coordinated and sent the GameBoy and several games, and it still ranks as one of the best gifts I ever received. I was a low ranking enlisted man whose biggest challenge while deployed was dealing with boredom, and the GameBoy was my main method of dealing with it. The second biggest challenge while being deployed was dealing with a complete and absolute lack of privacy, and the GameBoy helped with that too, providing a mental escape (while not actually escaping).  Before we left the country I had gotten quite good at Tetris and was able to see the Russian dancers and Buran Shuttle launch victory screens. It was also during that time that I first experienced the Tetris Effect, but at the time we called it being “Tetrisized”.  

Tetris remained my favorite GameBoy game for years, perhaps until I got out of the Army altogether. I never gave it much thought until recently when I started trying to program an AI to play the game. The AI Block Battle game is similar to Tetris, but not identical. The rules are similar enough that I thought that simply breaking down how I play the game into some kind of heuristic would be sufficient, and since I play the game very well I felt  it should be a pretty simple task to accomplish this. As usual, I was wrong. Very wrong.

At first I struggled to program a bot that could effectively clear rows without creating holes in the stack structure, and as a result it would lose very quickly. I solved this by assigning weights to certain aspects of a playing field and looping through all possible rotations and drops of the current piece to get the most advantageous game field score. This is, of course, a very naive approach and ignores many best fits for a piece. My scoring function looks at four aspects of a board position:
1. Structure height
2. Number of “holes” in the structure
3. Number of lines the move would clear
4. “Bumpiness” of the structure

Height, holes, and bumpiness are all weighted negatively, while clearing lines is weighted very positively. After some monkeying around with the weights for a while the bot started playing well enough that it clears lines mostly efficiently.

![MayoBot]({{ site.url }}/assets/images/MayoBot.png)

I named the bot **MayoBot** and uploaded the bot to Riddles.io, there is a story behind the name, but that is for another day. Over the course of week it rose up the ladder into the top 10 out of about 54 bots. This actually surprised me, because this version of the bot is about the simplest tetris playing AI possible other. It does take into account the next piece, but there are many parts of the game that it is not even attempting, such as not using skips, no T-Spins, no attempting to send garbage lines at all. All MayoBot does is try and survive. I even noticed some bugs in watching replays. When the height of the structure gets too high due to garbage lines the bot shits the bed and seems to play random moves and dies quickly.

I just checked and MayoBot is sitting in 6th place. I think this is more of an indicator of how hard it is to make an effective tetris AI that plays fast. Each bot only gets 10 seconds total of thinking time in their time bank, but gets an additional 200ms each turn. You can eat up 10 seconds pretty quickly, which is the main reason why my scoring function is so simple. When MayoBot was competing in the lower 30 of the ladder most opponents were timing out mid contest.  I think the top 15 or so seem to do a good job staying in the game to the end.

The next steps for MayoBot would be to come up with some strategies to send garbage lines to the opponent bot. That’s really the only way to move up the ladder some more.

If you're interested in creating an AI Block Battle bot of your own I created a starter bot
for the Go language which can be found on [github](https://github.com/adamadair/blockbattle-startbot-go). There are
links to other starter bots in other languages on the Riddles.io website. Google it.
