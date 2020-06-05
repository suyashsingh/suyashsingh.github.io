---
tite: "Reading Code"
pretty_title: "Reading Code"
layout: blog_post
readTime: 10 minute
tag: misc
description: Reading code if one of the essential skills in software development. This post shows you ways how you can read code effectively. Follow along to know the tools you can employ to make reading code easier.
post_intro: |
    **Isn't reading code as important as writing code?** Focusing on reading code makes sense rather than blurting out code(which by the way is called *art of creating bugs*). Reading code from a project can be a bit more complicated than it sounds but the benefits outweighs the initial efforts. You might be new to the language and its alien constructs mightcause a bumpy ride on understanding the code. A bit of persisten effort is all you need to analyze the code and learn out of it.  Here are some of the ways to make reading code easier for you.
---

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
    You can use tools like <a href="https://www.doxygen.nl/index.html" title="link to homepage of doxygen documentation tool" target="_blank">Doxygen</a> or <a href="https://www.sphinx-doc.org/en/master/" title="Sphinx Documentation tool homepage" target="_blank">Sphinx</a> to create documentation for undocumented projects(illegal in some countries). With the interim documentation in place you won't be immediately bogged down by the code.

+ ### Use tools for reading code
    You can use cross refferencers for figuring out the pieces in code.
    <a href="https://about.sourcegraph.com/" title="About Sourcegraph code search tool" target="_blank">Sourcegraph</a> is one such tool. I personally find it useful if you have to read code. Its a paid tool, but you can use their web based 
    version to dig into github repositories(only) for free. I know that ain't much and can't be used with local projects but anyways I wasn't promising a sivler bullet. Here's <a href="https://sourcegraph.com/github.com/cesanta/mongoose" target="_blank" title="try out source graph on mongose github repository">the link for demo of sourcegraph on the github repo of mongose</a> . See the link, you need to prepend `sourcegraph.com` before the link of the github repository.

Above all keep digging into the code.

**May the source be with you!**

