---
tite: "udev Rules"
pretty_title: "udev Rules"
layout: blog_post
readTime: 5 minute
tag: linux
description: udev rules can be set for managing hardware devices in linux. udev rules can be used to trigger scripts based on hardware events.
post_intro: |
    udev is a system of managing the entries in the `/dev` directory. The entries in `/dev` directories are special they are device files and not regular files. So if you have a uart to usb dongle plugged into your computer you will have one entry for it in the `/dev` directory.
---

## How is udev going to help?
Well basically you will have some control over these files. Basically kernel will 
create them on the fly when you insert a device.

What if you want to do some thing when a particular device is plugged in your
system? You could run a script as soon as you insert a usb to uart dongle. Or 
how about shutting down your pc as soon as some one inserts a pendrive in it!

So what you will have to do is create a udev rule for the device and add it to 
the system. 

## Sources for Learning udev
I found the following links useful for learning about the 
udev rules.

+ <a href="http://www.reactivated.net/writing_udev_rules.html" target="_blank" 
title="article on writing udev rules">This article on 
reactivated.net</a> explains a lot about writing udev rule and you can take it as a 
starting point on writing your own custom udev rules. 
Some of the commands used in the article has to be changed as they have 
been changed after the article was written. For eg. `udevinfo` written in the 
tutorial would have to be replaced by `udevadm info`.  
These commands might not run as such but is gives you a good base. 
You can refer <a href="https://www.tecmint.com/udev-for-device-detection-management-in-linux/" target="_blank" title="article on recent udev commands">this link for knowing the recent udev commands.</a>

+ <a href="https://lwn.net/Articles/65197/" target="_blank" title="email from Greg KH regarding udev">This email from Greg KH</a> on lwn is fun to read. Also if you want to know more you can read a paper on udev by the 
developer who created it.. guess who? Here’s the <a href="https://landley.net/kdocs/ols/2003/ols2003-pages-249-257.pdf" title="paper on udev" target="_blank">paper on udev</a>


## Use Cases
Having a usb device to mount always at a common mount point, or having a driver 
loaded automatically when the device is inserted can be a use case for writing 
your own udev rule.

If you have to work on making a usb device to mount on a particular mount point 
you can also use the exsisting package <a href="https://github.com/rbrito/usbmount" 
title="github repository of USB mount" target="_blank">USBmount</a>

Also, if you interested in triggering a script based on device insertion or 
removal event you will have to make sure that the script is small. Because udev 
would be waiting for your script to complete execution and other events would be
missed. **This is rude!** Also udev would kill your script after a timeout. The 
best way out of it is to have a background task – a systemd service do all the 
heavy lifting for you.

## Additional Resources
1. <a href="https://bootlin.com/doc/legacy/udev/udev.pdf" target="_blank" title="hotplugging using udev from bootlin">Hotplugging using udev from bootlin</a>.
