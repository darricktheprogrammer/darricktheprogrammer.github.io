---
Tags: languages, AppleScript
---

AppleScript as a programming language doesn't get much respect in the software industry. Even the people who don't hate it don't necessarily love it. At best, it's seen as a means to an end; grudgingly, The Right Tool For the Job. Personally, I don't love it like I used to. I've grown past its limitations and prefer to use Python when I can. But, as a developer who automates art manipulation in the Adobe Suite, working for a company that stores a lot of their data in Excel spreadsheets, my job would be a lot harder without it.


What's so great about AppleScript?
==
Obviously, AppleScript's biggest strength is its interoperability with almost all of the the applications on your system. No other language makes it so easy to create iTunes playlists based on the subjects of mail messages you receive between 3:00-5:00pm. And it does this while maintaining readability (I'm looking at you, Perl). Yes, some AppleScript code is easier to read than other code, but a lot of that comes down to application-specific dictionary implementations, which I'll talk about later.


Arguments I hear
==
**AppleScript isn't programming language**  
Bullshit. Of course it is. If I write a set of instructions, and that set of instructions gets compiled to byte code (even if it's at runtime), and those instructions are carried out by a computer, I'm using a programming language. If you can call [Brainfuck][4], [Chef][5], and [Whitespace][3] programming languages, then you can sure as hell allow AppleScript into that exclusive club of things that are officially considered good enough to be programming language.


**Ok, but it's more of a _scripting_ language**  
This is another bullshit argument. A scripting language _is_ a programming language. Are you going to tell me that PHP is not a programming language? What about Ruby? Python? While I realize there's a lot of debate on this point, I'll let [Stackoverflow answer for me][2].


**But, can it do [ FEATURE X ]?**  
All languages have strengths and weaknesses. Can Python do multithreading? Can I write a C program in less than 5,000 lines of code? AppleScript has a lot of the functionality that mainstream languages have. They may be a little difficult to use, but OOP, libraries, and modular design are all a built-in part of the language. JavaScript doesn't have OOP, but it's still widely accepted as a programming language. 


**AppleScript is so verbose!**  
Which makes it readable. One of the big examples that people point to on this argument is assigning a variable: `set x to 5 + 1`. However, no one seems to make that argument against Lisp: `(let (x (+ 5 1)))`. The AppleScript version is not only 28% shorter, but much more readable.

And lets not pretend this is actually an AppleScript issue anyway. Excess verbosity is a trademark in Apple programming. When's the last time you looked at Objective-C? It is every bit as verbose as AppleScript if not more so. Do a search for "Objective-C verbosity" and see if you come away with the same amount of complaints, though. Nope. People are pretty willing to let that one slide.

If you don't like big verbose commands, you don't even have to use them. A pretty standard beginning AppleScript example reads something like this: `set the name of myDocumentFile to newDocumentName`. But, you're not a beginner. If you hate that syntax, act like a grown-up and modify your usage of the language to something you're a little more used to: `set name of f to newName`. Don't blame AppleScript for the fact that you're using beginner tutorials and not applying logic to how you should actually be using them.


**The language is so inconsistent between programs**  
Ah! You got me on this one. But, I don't give full blame to AppleScript on this. Pretend for a second that we're talking about the UI instead of AppleScript.

Apple has painstakingly compiled over 300 pages of information called the [Human Interface Guidelines][6], meant to keep the UI consistent across all programs on the OSX platform. All the way down to [What perspective your app's icons should be viewed from][10]. But...

Have you ever used a Java program on the Mac? How was the UI? Was it the wonderful Apple experience you come to know and love? Or did it look like it was built in 1998? Did all your keyboard shortcuts work, or did you find that you worked slower because you had to mouse click everything? Did you blame Apple for that, or did you blame the developer? As much as Apple tried to create consistency on their platform, some people just can't be bothered, which leads to crappy Java UIs.

The same happens with AppleScript. Apple can lay out all the guidelines they want, but what the developers actually _do_ is still up to the developers. AppleScript was specifically designed with a small core and the ability to be extended by third-party programs. That leaves a lot of space for the developers of those programs to do basically whatever the hell they want. Some programs (and what I mean here is software designers) are good at categorizing and naming elements in a way that makes sense. Adobe Illustrator is one of these programs. If I want to get the color of a path, I just say `color of path item 1`. It couldn't be more intuitive.

On the other hand, Microsoft Excel's dictionary is... not as intuitive. Or as clean. In Excel, everything's an "object". Not just in function, but in name: `font object`, `interior object`. What's an interior object? According to the Excel Dictionary it's "an interior object that represents the interior of the specified object." Oh. Ok, then what's an interior? "Represents the interior of an object." Ah. Got it. Totally makes sense.<sup>1</sup>

Excel's dictionary has nothing to do with AppleScript. It is purely a Microsoft problem. Whoever designed their AppleScript support did not do a good job at defining the objects in a way that is useful to those trying to access them with AppleScript.

<sub>1. In case you're curious, the `Interior Object` controls the visual properties of an object, such as color, pattern, tint/shade, etc. Personally, I think `formatting` or `format properties` would have been a better name.</sub>


**So, you're saying AppleScript is the cat's balls?**  
Um... I don't know if that's a complement or not. So, no. That's not what I'm saying. AppleScript is built on Apple's Open Scripting Architecture [(OSA)][7], which was built to be an abstraction layer that allows the ability of any language to command an application. It just happens that AppleScript is currently the only official OSA Language supported by Apple. There was a [Javascript implementation][8] built by Mark Aldritt at [Late Night Software][9], but it was never updated from the Carbon framework to Cocoa.

I would love to see Apple expand the the number of official OSA languages, adding in more popular and robust languages. Personally, Python would be my first preference, but Ruby or Javascript seem like more likely candidates. I doubt it will happen though, unless people start raising a fuss for it. Until then, we're left with what we have. Which could be worse. Unless you want to create those iTunes playlists in Brainfuck.


[2]: http://stackoverflow.com/a/110284/2348587
[3]: http://compsoc.dur.ac.uk/whitespace/index.php
[4]: http://www.muppetlabs.com/~breadbox/bf/
[5]: http://www.dangermouse.net/esoteric/chef.html
[6]: https://developer.apple.com/library/mac/documentation/UserExperience/Conceptual/AppleHIGuidelines/Intro/Intro.html
[7]: https://developer.apple.com/library/mac/documentation/AppleScript/conceptual/AppleScriptx/concepts/osa.html
[8]: http://download.cnet.com/JavaScript-OSA/3000-2247_4-5653.html
[9]: http://www.latenightsw.com/
[10]: https://developer.apple.com/library/mac/documentation/UserExperience/Conceptual/AppleHIGuidelines/IconsImages/IconsImages.html#//apple_ref/doc/uid/20000967-TPXREF106
