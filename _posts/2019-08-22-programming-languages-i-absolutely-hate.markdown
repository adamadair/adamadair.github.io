---
layout: post
title: "Programming Languages I Absolutely Hate"
date: "2019-08-22 10:22:23 -0500"
---
Before I begin to spew forth hate on several vile programming languages I just
want to make sure that you know that I know that this is MY OPINION.
I also want you to know that I am aware that many fine pieces of software have been
written using these languages, and that my hatred for them is probably because
I'm a big-stupid-dummy-head who doesn't know what he's talking about. Of this,
I am keenly aware. Be that as it may, I am forging ahead.

# JavaScript
JavaScript is a shit programming language. This really isn't opinion. This is actually fact, and it is well documented on the
web about how terrible JavaScript is, and I'm not going to rehash that. If you
don't believe me, [start with this article](https://walkercoderanger.com/blog/2014/02/javascript-minefield/),
then do some Googling on your own.

Try watching this [video](https://archive.org/details/wat_destroyallsoftware). Or [this one](https://www.youtube.com/watch?v=xE8tL8NdHaY).

My hatred for JavaScript has burned for over 20 years, and I have written miles
and miles of this horrible stuff. I work with JavaScript on a regular basis, and
over the course of a 23 year professional programming career I would say it is my #2 for
number of lines written. Every day that I am a subjected to working with JavaScript I can't help but think
this thought:  There has to be a better way!

The thing about JavaScript that sets it apart from the other programming languages
I hate is that there seems to be some sort of mass psychosis about JavaScript, and
all programmers have been brainwashed into thinking JavaScript is great general
purpose programming language. Either that or everyone is pretending it isn't
awful. What began as a scripting language to interact with HTML documents is now the #7 language in the [TIOBE index.](https://www.tiobe.com/tiobe-index/), and this baffles me. It is a scripting language, and bad one at that.

I'm writing this post in an editor written in JavaScript, Atom. Atom is a regular pain in the ass, but it's free. It also uses a crazy amount of memory and CPU, so the only thing I use if for is editing Markdown.  Atom is built with Electron which is library that allows you to build
Build cross-platform desktop apps with JavaScript, HTML, and CSS, to which I say:  Great! Let's bring the shittiness of web development to the desktop. That makes complete sense.

I took a course on Electron, and I quit in the middle of the class. It was obvious that I would never
waste my time trying to use it. Electron is way more complex than any other GUI
technology I've ever had to program in. If you've ever made an GUI in any other technology (think VB, WebForms, WPF, Swing, Qt, GTK+, etc..)
you'd realize Electron is horribly complex and difficult to even get a project started. The main problem I have with Electron is that
it doesn't actually solve a problem. The ability to easily make cross platform applications already existed, and it wasn't that hard.
Electron does the same thing, but it makes it harder to do. Things should be getting easier, not harder. The programmer that would select Electron over anything else, would be the programmer that only knows JavaScript, HTML, and CSS.

Microsoft made Windows programming super simple with Visual Basic back in the 90s. Laying out a
UI and hooking it up to code has never really been easier than that. WPF and XAML
reduced the amount of code required to define complex GUIs, but in the process added some complexity that made it difficult to adopt.
Cross platform UIs are more difficult to achieve, but Java Swing was pretty good in its day,
and there were IDEs that made laying out a good UI and hooking it up to code pretty easy. The migration to all UI having to be on the web has actually made application development harder not easier. It takes way more code to achieve something simple in a web app than
its WebForm, WPF, or Java Swing counterpart.

# Perl
I spent several years in the mid-2000s as a UNIX/Linux sysadmin, and during that
time I learned 2 things:
1. I am a terrible sysadmin. Just awful.
2. The Perl programming language.

Having been out of the sysadmin game for so long I have no idea how things are now,
but at the time I was doing the job Perl was in wide use for automating tasks
on servers. I took the opportunity to go to Perl class, and I still have that book too! Perl 5 syntax
is strange compared to other programming languages. My hatred of Perl was not
in having to learn or write Perl code, but in having to read Perl code others
had written. Perl code written by other programmers is difficult to read, and has been described by some programmers as resembling "Line-noise".
I even found that having to go back and decipher Perl that I had written months earlier was difficult to do.
The amount of Perl I had to deal with in the sysadmin job was small, and it did not contribute greatly
to my overall dissatisfaction of the job. I eventually left the sysadmin job for a programming
job working with .NET.

What I didn't know at the time was that Perl had been getting popular for making web apps. This
would not have concerned me at the time, because I was enjoying life with C#, a language
that just makes sense. I eventually took a job that was mainly .NET work, but I also had to
support a web app written entirely in Perl. That Perl code base was something that was
purchased from a vendor and it was purposely coded in an indecipherable style ensure that maintenance contracts would always be required.
Any sort of maintenance work regarding that application sent my way was always
met with a large amount of procrastination because reading that code hurt by brain.
It was a terrible experience that has landed Perl as the second least favorite
language of all time.

In 2017 it was reported that [Perl was the most hated programming language](https://www.theregister.co.uk/2017/10/31/perl_most_hated_language/).
I don't know how Perl could be more hated than JavaScript, but there you go.

# Visual Basic for applications
VBA is the last language I'll complain about here. I only ever had one project involving
VBA. It would be difficult to describe the nature of the project without leaking some information about
my employer that might not be in anyone's best interest. All I am comfortable in saying is that the script I developed
ran in a product that was not even a Microsoft product, and it worked as designed and
met my employers requirements nicely and the customers who used it would not have even known about it.

Then the [Melissa virus](https://searchsecurity.techtarget.com/definition/Melissa-virus) happened. After that there was a whole bunch of similar
macro viruses, all written in VBA, which targeted stupid users with email address.
It is a well known fact that stupid users with email addresses far outnumber smart users with email addresses, and as result, hilarity ensued
Once things got sufficiently hilarious the decision was made that VBA Macros had
to be locked down. This caused me work problems, which was annoying,
but it was hard to argue against.

My problem with VBA is not the language itself, but the sheer stupidity or
perhaps naiveté with which it was implemented in the products that Microsoft
put it in, especially the Outlook product. The ability to steal data from
unsuspecting users and use that data against the user and all the contacts of that user
was built right into the product, apparently without any concern at all.

There is a reason why nobody has even suggested using VBA in any project that
I have worked on since.
