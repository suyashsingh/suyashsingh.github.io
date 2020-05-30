---
tite: Trying out logic analyzer
post_page_title: Trying out Logic Analyzer
layout: blog_post
readTime: 5 minute
category: Embedded
tag: embedded
---

Finally I got my hands on a USB Logic Analyser. I bought a 24 Mega Hertz 8 
channel USB logic analyzer from robu.in. I also bought additional test probes as well.
The device is cheap and might be useful in reverse engineering electronics. 

## Specifications
+ Interface: USB
+ OS: Windows & Linux with [Logic analyser software from saleae](https://www.saleae.com/downloads/).
+ Voltage Range: 0 to 5V

There is no input protection so if you mess things up you are surely going to regret it.
Chances are you would blow up your usb port. If you want to be safe you should
buy a Optically Isolated USB Hub as a security measure.

## Usage
The usage is simple all you need to do is install the saleae software and it would
automatically detect the device model. Then all you need to do is make connections
and start taking samples. It would show a pretty graph for the signal under analysis.

You can add a protocol analyser on to a particular signal and it would decode the signal
for you.

![Screenshot for Saleae Logic Software](http://i.imgur.com/FxUIuF2g.png)

## Links
You can get logic analyzers from `amazon.in` as well. I got them from `robu.in`
+ [USB Logic Analyser](https://robu.in/product/usb-logic-analyze-24m-8ch-mcu-arm-fpga-dsp-debug-tool/)
+ [Test Hooks](https://robu.in/product/8ch-quality-test-hook-clip-logic-analyzer-test-folder-usb-saleae-24m/)


