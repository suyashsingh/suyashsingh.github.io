---
tite: Reading Code
post_page_title: Reading Code
layout: blog_post
readTime: 10 minute
category: dev
tag: devtools
---

**Isn't reading code as important as writing code?** I guess focusing on reading code makes sense rather than blurting out code(which by the way is called *art of creating bugs* and trust me its the new trend in town). Reading code from a project can be a bit more complicated that it sounds. You might be new to the language and its constructs might be affecting your comprehension.  Here are some of the ways that can make your life a bit easier.

## Run the code
Download the code and run it. You would figure out the dependencies, the build system and many other things in the process that would aid you in getting a better understanding of code.

## Figure out the high level logic
Instead of figuring out why is a pointer passed to a function, knowing what the function is doing on a broader level might help you get a picture what is happening. After that all that left is peeking under the hood. *Having an over all picture of high level logic is important.*

## What makes you tick?
Now that you have figured out what and how the project is working on a broader level you can zoom in now into the nitty grities. This might be overwhelming as you might be clues less where to dig in. Remember anything simple which you can follow would be fine. You need to find one spot that you feel like is simple enough and you need to run through its entire chain of action. Since a program is a logical entity things would be interlinked, things would start making sense eventually. *In short you need to find one thing that you like in the program and trace it back and forth in the entire project.*

## Still ain't making sense!
Well it might take some time. Here are some more things that you can do:

+ ### Use an Editor
    Use an editor with syntax highlighting for the language that you are working in. With an editor you can move through function   declarations, find its refferences and so on. Examining library and function calls made in the application can be one of your strategies.

+ ### Create Documentation if there isn't any
    You can use tools like `doxygen` or `sphinx` to create documentation for undocumented projects. With the documentation in place you won't be immediately bogged down by the code.

+ ### Use tools for reading code
    You can use cross refferencers for figuring out the pieces in code.
    `Sourcegraph` is one such tool. I personally find it useful if you have to read code. Its a paid tool, but you can use their web based 
    version to dig into github repositories(only) for free. I know that ain't much and can't be used with local projects but anyways I    wasn't promising a sivler bullet. Here's <a href="https://sourcegraph.com/github.com/cesanta/mongoose" target="_blank">the link for demo</a> of sourcegraph on the github repo of mongose. See the link, you need to prepend `sourcegraph.com` before the link of the github repository.

Above all keep digging into the code.
**May the source be with you!**

