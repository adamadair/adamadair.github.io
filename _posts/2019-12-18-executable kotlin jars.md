---
layout: post
title: How to create executable kotlin jars
date: 2019-12-18 12:13
category: Programming 
author: Adam Adair
tags: [Kotlin Programming]
summary: 
---

I've been oscillating back and forth in my personal projects between using the Go and Kotlin programming
languages. The one advantage Go has over all the other languages that I program in is that building
an executable binary file is very easy Because of how Go relies on static linking is is almost assured to continue
function correctly regardless of any software updates. On the complete opposite end of the spectrum 
is Java and its wacky way of handling binaries. I don't want to waste time dredging up everything I 
dislike about the JAR, but JAR hell is way worse than DLL hell in my opinion. 

I'm completely sold on Kotlin being a better programming language than Java, but when it comes to executable JARs 
I find Kotlin to actually be worse. If you write a command line app in Kotlin and want to deliver it as an
executable JAR there is little information in the Kotlin documentation on how to do this, but if you're 
like me and you rely on Gradle to handle your Java and Kotlin builds then it's even worse. From what
I can gather the problem is this: Compiled kotlin program depends on the standard Kotlin library. This 
actually makes sense, but where I have a problem is that I can't find documentation on how to go about adding the
Kotlin standard library to the classpath.  

Taking a page out of the Go Language playbook, we can add the standard library to the JAR file that
gets build by gradle. When you add dependencies to your JAR file the resulting file is called a fatJAR
or and uberJAR. These seem like silly names, and I support that. 

When you initialize new Kotlin application project with Gradle, and you finish writing super fine code that 
won't rust, bust, or collect dust and you let gradle build the jar file you won't be able to run it with 
the `java -jar` command. You will get an error similar to "Exception in thread "main" java.lang.NoClassDefFoundError: kotlin/jvm/internal/Intrinsics"
As mentioned before you can fix this by adding the Kotlin library to classpath.  My preferred method of 
fixing this is creating the uberJAR. To do this I add the following to the end of my build.gradle.kts file.

```
val jar by tasks.getting(Jar::class) {
    manifest {
        attributes["Main-Class"] = "MainKt"
    }
    archiveClassifier.set("uber")

    from(sourceSets.main.get().output)

    dependsOn(configurations.runtimeClasspath)
    from({
        configurations.runtimeClasspath.get().filter { it.name.endsWith("jar") }.map { zipTree(it) }
    })
}
```

And with that, the Kotlin standard library (and any other dependencies) will be included in the jar. As you
can imagine it creates a very large jar file. For example, I had a program that originally created 
a 7kb size normal jar file, but the uberJAR file was 1.2 MB in size, which is a large difference. 

Some things to note here, the MainKt class name will have to be replaced with your actual Java class
name, which can be difficult to figure out if you're new to Kotlin. I always create the main method
in file named main.kt without any package, and that is why my main class is always "MainKt". This is
my own SOP and I wouldn't necessarily recommend it, but it is convenient.

This method also has the added benefit of not requiring someone to install kotlin to run your program.

