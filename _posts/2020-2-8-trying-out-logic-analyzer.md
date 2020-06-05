---
tite: "Trying out logic analyzer"
pretty_title: "Trying out Logic Analyzer"
layout: blog_post
readTime: 5 minute
tag: embedded
description: I recenty got to try out usb logic analyser. Here are my views on logic analyzers
post_intro: |
    Finally I got my hands on a USB Logic Analyser. I bought a 24 Mega Hertz 8 channel USB logic analyzer from robu.in. I also bought additional test probes as well. The device is inexpensive and useful in reverse engineering electronics.USB Logic Analyzer are inexpensive and handly tool for debugging embedded system. Here's my experience
    on tyring out a usb logic analyzer.
---
 

## Specifications
+ Interface: USB
+ OS: Windows & Linux with <a href="https://www.saleae.com/downloads/" title="pc software for logic analyzer from saleae" target="blank">Logic analyser software from saleae</a>.
+ Voltage Range: 0 to 5V

There is no input protection so if you mess things up you are surely going to regret it.
Chances are you would blow up your usb port. If you want to be safe you should
buy a Optically Isolated USB Hub as a security measure.

## Usage
The usage is simple all you need to do is install the saleae software and it would
automatically detect the device model. Then all you need to do is make connections
and start taking samples. It would show a pretty graph for the signal under analysis.

You can add a protocol analyser on to a particular signal and it would decode the signal
for you. The software interface looks something like this:

<img alt="d" src="{{ "/assets/images/blog-posts/saleae-logic-software-interface.png" | relative_url }}" alt="Saleae logic software interface" class="img-fluid">

## Links
You can get logic analyzers from `amazon.in` as well. I got them from `robu.in`
+ <a href="https://robu.in/product/usb-logic-analyze-24m-8ch-mcu-arm-fpga-dsp-debug-tool/" title="USB logic analyzer from robu.in" rel="nofollow" target="_blank">USB Logic Analyser that I bought from robu.in</a>
+ <a href="https://robu.in/product/8ch-quality-test-hook-clip-logic-analyzer-test-folder-usb-saleae-24m/" title="Logic Analyzer test hook from robu.in" target="_blank">Test Hook for logic analyzer</a>
