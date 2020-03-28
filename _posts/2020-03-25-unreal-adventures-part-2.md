---
layout: post
title: Unreal Adventures - Part 2
date: 2020-03-25
category: Programming 
author: Adam Adair
tags: [Unreal Engine]
summary: Building the engine
---

What follows is my experience attempting to build Unreal Engine 4.24 from Epic Games on Linux.

1. Get Beer. Hamm's beer is a good beer for building software. It's America's classic premium beer, born in the land of sky blue waters, and it is quite refreshing. 

2. Open beer.

3. Drink beer.

4. Read install [document](https://docs.unrealengine.com/en-US/Platforms/Linux/BeginnerLinuxDeveloper/SettingUpAnUnrealWorkflow/index.html). This is actually a good install document!
   
5. There are some things you need prior to getting busy:
   1. GitHub account - check
   2. Epic Games account - check
   3. Read and accept the EULA - right, I totally did that.

6. Connect GitHub account to Epic Games account. This part confused me for a bit. I did everything as described in the document but there is a piece that they seem to have left out. I followed the steps and I waited and waited but the Unreal Engine project never showed up for me in GitHub. I noticed I received an email stating I had been added to the GitHub project and I had to click on a link in the email to confirm. Once I did that, then everything worked fine.

7. Clone the project from git hub. This took 20 minutes and 48 seconds. I've never checked out a project quite that big before. I got bored. I know what I said in the last post, but I did, I really got bored.

8. Open another beer.

9. Run Setup.sh. Fucking hell! That took 17m and 12 seconds. We're almost 40 minutes into this and we haven't even gotten to the compile step yet. I am seriously rethinking this whole Linux only thing. 
    
10. Open another beer.
    
11. Run GenerateProjectFiles.sh.
    
12. While it's generating project files start making a little pyramid with beer cans. Hey, this part only took 3 minutes and 7 seconds! 
    
13. Run make. Now we're getting somewhere.
    
14. This part they actually warn may take some time, so I take the opportunity to crutch my ass to the restroom, then get another Hamm's beer.
    
15. Admire the pyramid.
    
16. Startup the XBox and play some State of Decay 2, which interestingly enough was made with Unreal Engine 4.
    
17. About an hour later I rage quit State of Decay. Check on the compile progress...still chugging away. Go put on pajamas, and...you guesed it...get another beer. 
    
18. 205 minutes and 40 seconds later...it's done. Time for a test run! Oh for love of Pete! It starts initializing then at 18% initialized it stops, and it looks like it hangs. Apparently it is verifying global shaders, and that must take the better part of forever. I can't drink anymore beer. I have to work tomorrow. Maybe I'll get caught up on my correspondence. Who needs a letter from me?
    
19. It's now stuck at 45% and it's compiling something or other. I've lost track of how much time it has taken. I'm ready for bed. I started at about 7 pm, and it's now after midnight. I have to work in the morning, even if it is from home. I'll have to pick it up in the morning. As I head to bed it has 2997 shaders left to compile.