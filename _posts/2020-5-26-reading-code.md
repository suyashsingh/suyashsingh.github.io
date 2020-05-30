---
tite: Reading Code
post_page_title: Reading Code
layout: blog_post
readTime: 10 minute
category: dev
tag: misc
---

**Isn't reading code as important as writing code?** I guess focusing on reading code makes sense rather than blurting out code(which by the way is called *art of creating bugs*). Reading code from a project can be a bit more complicated than it sounds. You might be new to the language and its alien constructs might cause a bumpy ride on your path to comprehension.  Here are some of the ways for making your life easier.

## Run the code
Download the code and run it. You would figure out the dependencies, the build system and many other things in the process that would aid you in getting a better understanding of code.

## Figure out the high level logic
Instead of figuring out why some pointer is passed to a function, knowing what the function is doing on a broader level might help you get a picture what is happening. After that all you need to do is peeking under the hood. *Having an over all picture of high level logic is important.*

## What makes you tick?
Now that you have figured out what and how the project is working on a broader level you can zoom in now into the nitty grities. This might be overwhelming as large projects seem almost impenetrable. Remember anything simple which you can follow would be fine. You need to find one spot that you feel like is simple enough and you need to run through its entire chain of action. Since a programs are logical entities things would be interlinked, they would eventually start making sense. *In short you need to find one thing that you like in the program and trace it back and forth in the entire project.*

## Still ain't making sense!
Well it might take some time. Here are some more things that you can do:

+ ### Use an Editor
    An editor with syntax highlighting for the language that you are working in could do wonders. With it you can move through function   declarations, find its refferences and so on. Examining library and function calls made in the application can be one of your strategies.

+ ### Create Documentation if there isn't any
    You can use tools like `doxygen` or `sphinx` to create documentation for undocumented projects(illegal in some countries). With the interim documentation in place you won't be immediately bogged down by the code.

+ ### Use tools for reading code
    You can use cross refferencers for figuring out the pieces in code.
    `Sourcegraph` is one such tool. I personally find it useful if you have to read code. Its a paid tool, but you can use their web based 
    version to dig into github repositories(only) for free. I know that ain't much and can't be used with local projects but anyways I    wasn't promising a sivler bullet. Here's <a href="https://sourcegraph.com/github.com/cesanta/mongoose" target="_blank">the link for demo</a> of sourcegraph on the github repo of mongose. See the link, you need to prepend `sourcegraph.com` before the link of the github repository.

Above all keep digging into the code.

**May the source be with you!**

