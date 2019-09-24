---
layout: post
title: "Golang Fun: Coders Strike Back!"
date: "2019-09-24 11:50:44 -0500"
---
I've recently been learning Kotlin and I was looking for a site where I could practice
my new found skills when I came across the CodinGame site. This is a site where
you play games by writing code. This combines two of my favorite activities!

One of the games is called "Coders Strike Back" which is a Star Wars based
game where you program the AI Bot for a pod racer and race it against other
peoples creations. For this challenge I reverted back to the Go programming
language for two reasons:
1. I am slightly more familiar with Go
2. Go performs way better than Kotlin

One of the interesting features of CodinGames is the ability to sync your
code online with a local file, which allows you to use your own IDE for programming.
I love the Goland IDE from JetBrains so this worked out well. Everytime you save
the file locally it gets replicated into the online environment. No more ctrl-c
ctrl-v business like with other sites.

The input to the bot comes from standard input, and out can log trace data to
standard error to get some feedback on what the bot is doing. I learned some
things about Go that I will use in all my bots from now on.

You can set the Go log library to send log data to standard error using the
SetOutput function

```
log.SetOutput(os.Stderr)
```
Simply using the Go logging I was able to get second by second telemetry
data from by bot which looked like:
```
2019/09/24 16:40:12 Location: 13025,6284
2019/09/24 16:40:12 Checkpoint: 12708,7105
2019/09/24 16:40:12 Checkpoint Distance: 880.000000
2019/09/24 16:40:12 Checkpoint Angle: 12.000000
2019/09/24 16:40:12 Opponent: 6800,1599
2019/09/24 16:40:12 Opponent Distance: 7791.010846
2019/09/24 16:40:12 Has boost: false
2019/09/24 16:40:12 Shield Cooldown: 0  Shield Pops: 1
```

The other thing I learned to do was test by bot using the Go test framework
by changing the input stream from standard in to a byte stream I controlled
with strings. The following is a test case where I test if the bot is going
to turn on shields:

```
func TestPodShields(t *testing.T) {
	pod := NewPod()
	for k, v := range tests {
		pod.Input = strings.NewReader(v.pod_input)
		pod.Update()
		if m:=pod.GetMove(); v.expected != m {
			t.Errorf("Error Test #%d: Incorrect move. Expected '%s', Received '%s", k,v.expected,m)
		}
	}
}
```


My bot beat the Silver League boss today for the first time. It starts out slow
but if you watch the replay you can see where he makes his move and takes over
the lead until the end of the race:

[My Replay](https://www.codingame.com/replay/409362217)

I find this kind of activity more fun than actually playing games.
