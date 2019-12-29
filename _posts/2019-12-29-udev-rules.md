---
tite: My second Post
post_page_title: udev rules
layout: blog_post
readTime: 5 minute
category: Linux
tag: udev, system programming, embedded linux
---

udev is a system of managing the entries in the /dev directory. The entries in 
/dev directories are special they are basically device files. So if you have a 
uart to usb dongle plugged into your computer you will have one entry for it in
the /dev directory.

## How is udev going to help?
Well basically you will have some control over them. Basically kernel will 
create them on the fly when you insert a device.

What if you want to do some thing when a particular device is plugged in your
system? You could run a script as soon as you insert a usb to uart dongle. Or 
how about shutting down your pc as soon as some one inserts a pendrive in it!

So what you will have to do is create a udev rule for the device and add it to 
the system. 

## Resources
I found the following links useful for learning about the 
udev rules.

+ [This article](http://www.reactivated.net/writing_udev_rules.html) on 
reactivated.net explains a lot about writing udev rule and you can take it as a 
starting point on writing your own custom udev rules. 
Some of the commands used in the article has to be changed as they have 
been changed after the article was written. For eg. udevinfo written in the 
tutorial would have to be replaced by udevadm info.  
You can run the commands as 
such from the article but is gives you a good base. 
You can refer [this link](https://www.tecmint.com/udev-for-device-detection-management-in-linux/)
for knowing the recent commands.

+ This email from Greg KH on lwn is fun to read . Also if you want to know more 
you you read a paper on udev by the developer who created it.. guess who? Here’s 
the [link for the paper.](https://landley.net/kdocs/ols/2003/ols2003-pages-249-257.pdf)


## Use Cases
Having a usb device to mount always at a common mount point, or having a driver 
loaded automatically when the device is inserted can be a use case for writing 
your own udev rule.

If you have to work on making a usb device to mount on a particular mount point 
you can use the package [USBmount.](https://github.com/rbrito/usbmount)

Also if you interested in triggering a script based on device insertion or 
removal event you will have to make sure that the script is small. Because udev 
would be waiting for your script to complete execution and other events would be
missed. This is rude! Also udev would kill your script after a timeout. The 
best way out of it is to have a background task – a systemd service do all the 
heavy lifting for you.

## Additional Resources
1. [Hotplugging using udev from bootlin.](https://bootlin.com/doc/legacy/udev/udev.pdf)