---
layout: post
title: "Linux Pains"
date: "2019-05-31 16:58:03 -0500"
---
From June to December 2018 I worked from home every day. The reason I had to
do this is a story for another day, but over that time I really grew to enjoy
teleworking from home. I'm a software developer, and I spend most of my time
programming. My employer provides me with a minimal desktop computer and some decent
software tools to do my job, but a problem for me is that desktop remains physically
with my employer. To use it from home my employer provides me with VPN access
to their network so that I can connect to my work computer from my home personal
computer using remote desktop. This took a couple weeks to get used to, and initially
my performance suffered, but eventually my productivity recovered to normal levels.
The main problem with this arrangement was my own personal computer which I purchased
in June of 2018. This computer was brand new from Best Buy when I started teleworking,
but soon after I bought it I started having problems  in the form of
the Blue Screen of Death which would show itself almost every day while I was working at least once. It was annoying,
but I never really lost any work because the work was on the remote computer.

I spent time troubleshooting it as a hardware problem, and I tested the memory and disk
repeatedly but never could find a hardware problem. I never figured out the problem and I eventually went back to the
office in December and thought that perhaps my computer problems would be over if I didn't have to use VPN,
but I was wrong. The frequencies of the blue screens seemed to increase. In February I was
getting blue screens about 30 seconds after login half the time. The consensus opinion
of the people I consulted was to rebuild the system. So I did. But instead of installing Windows 10
I rebuilt it with the Linux distro Ubuntu MATE 18.04. This took care of the Blue Screen of Death
problem, but what I overlooked at the time was my ability to access my work
computer from home. There was a Linux version of the VPN client, but I couldn't get it to launch in Ubuntu.
I had a MacBook Pro from 2011 that I could use in a pinch, to access my work desktop but that was it. I rarely
had a reason to work from home anymore so I didn't worry about it until today. I
had to be home in the afternoon for 4 hours and I really needed to get some work
done. I HATE using laptops. I find using a laptop to write software like trying
to play basketball with your dominant hand tied behind your back, it kind of
works but not well. I really only use it to write code if I'm watching
TV or a movie with my wife.

Today I was determined to figure out the problem with accessing my work from my
Linux computer. I started with the VPN client, because that seems like the almost
obvious place to start. After a little searching the internet I found that nobody seems to
be able to use this VPN client on current Ubuntu because it doesn't work with newer versions
of the Qt library. This has not been the first time Qt has been a pain in my ass,
and it kind of points out the main problem with desktop Linux. Once you venture outside of your
distributions package manager you are inviting a world of problems. I still get excited
when unmanaged software works flawlessly the first time I try to use it on Linux. I've been
a Linux enthusiast for over 20 years, and the desktop experience has gotten much
better over that time, but the user experience is still not quite at the level
that Mac or Windows users expect.

From what I was reading I was going to have to install an older version of Qt,
and make it the default version to get the VPN client up and running. I downloaded a number of Qt packages, installed
stuff, moved files, edited other files, blah, blah, blah...fuck Qt! After a couple hours I gave up,
and resolved to punch the first developer I meet that actually uses Qt. This is a
horrible product and it must die. I'll take the slow road to victory, one nose
at a time.

My next idea was to use a Windows in a VM. I downloaded and installed Oracle VirtualBox,
and then created a Windows 10 guest. This took way longer than I expected. I test
out new Linux distros often using VirtualBox and I am used to installing the
entire OS and getting up and running in less than 20 minutes. The Windows 10 install
took over an hour and the base Windows 10 installation is a disk hog. There really should
be a smaller and simpler option for windows users that don't want the full Windows
experience.

When I first logged into the virtual Windows 10 session the performance was terrible. It was completely unusable,
and I was getting discouraged because I thought I wasted another hour for nothing.
Looking at the task manager I could see that Cortana and
OneDrive were using almost 100% of the CPU. These processes are completely
unnecessary for my needs so I killed and disabled them and suddenly performance was acceptable.

Next I installed the VPN client on the Windows guest, and it worked super fine.
I was able to remote to my work desktop and Launch Visual Studio 2019 without
any problems, and the performance is surprisingly good. Not great, but acceptable.

The VDI file is at 12GB right now and while the VM is running it averages about 34%
CPU usage, but memory usage was lower than I expected. So 12GB and a fairly high CPU load is the cost to remote to my work computer using
this solution. It would have been preferable to find a total Linux solution,
but at least now I can write work code on one screen an watch Netflix on the other and I
haven't had any problems yet, so I'll count this as a win.
