---
tite: "Beagle Bone Black Introduction"
pretty_title: "Introduction to Beagle Bone Black"
layout: blog_post
readTime: 5 minute
tag: [beagle-bone-black, bbb, embedded-systems]
description: This post is about briefly introducion Beagle Bone Black from TI for learning embedded linux.
post_intro: |
    Beagle Bone black is an open-source embedded linux development board from Texas instruments. You might would have heard about Raspberry Pi it is very similar to RPI, infact the both fall under the category of SBC a.k.a Singble Board Computer. The area were Beagle Bone Black shines is that it is truly opensource. Lets explore more about it.
---

`Note: This document is work in progress. I will keep updating it as I experiment more.`

## Beagle Bone Black: What it isn't?
1. **Ease of Use**  
	Beable Bone isn't meant for ease of use. What I mean by that is you might struggle to install
	maybe even simple packages in BBB. Raspberry Pi on the other hand is very simple to use and the
	Linux distribution you get with it is very well documented. 

	So is Raspberry Pi better than Beagle Bone? Nope they both are aimed at very different audience.
	RPI is used as a very accessible tool for teaching computer science and basic electronics, and it
	definitely shines at it. Beagel Bone on the other hand aims to give you complete access to the hardware.
	You will readily find all the supporting documents for the System on Chip(SoC) used on a Beagle bone.
	RPI isn't that great at sharing those details. You can get the data sheet, board schematics, etc 
	for the AM335x SoC used on BBB. This gives you the flexibilty to do almost with a Beagle Bone.
	To give you an example you can change the bootloader used on BBB, put on your own linux kernel, or if
	you wanna go nuts you could write your own bootloader and your own Operating system and run it on 
	a beagle Bone. However please keep in mind that some of these things can also be done on a Raspberry Pi.


	<img src="{{ "/assets/images/blog-posts/beagle-bone-black.webp" | relative_url }}" alt="Beagle Bone Black Rev.C Board" class="img-fluid">


2. **Perfomance vs Price**  
	If you compare the performance you get out of the amount that you spend, RPI would probably be better.
	For instance is you see Beagle Bone Black Rev.C board it has a Single core processor. RPI however is usually
	quad core. But the price you are spending on Beagle bone black is for something else: the flexibitly.

3. **Learning Embedded Internals**  
	This is were you would fall in love with the beagle bone:
	-  You can learn how linux works, compile the linux kernel etc.

	-  Learn about ARM Application Series processor. Since the User Manual is open you can cross relate
		everything that you learn about ARM architecture (e.g. ARM V8).

4. **Embedded Linux**  
	 You can create your own linux images with bootloader of your choice, the
	root file system you like and much more. To name a few tools that you can get hands on with beagle
	bone black hardare - yocto, buildroot, uboot, busybox and so on.

5. **Learn Linux Kernel Internals / Linux Device Driver Development**  
	You can write custom drivers, learn how I2C protocol works, etc. Say for the I2C example you can
	learn how to write slave drivers and also the I2C controller driver on the SoC. Isn't it fun!(and probably scary too!)

## Beagle Bone Black: An Embedded Systems Learning Tool
If you want to get a hands on a ARM SoC, learn to write linux device drivers, kernel development, bootloader
development and more. Beagle Bone black is an excelent learning tool for Embedded Systems.

Hope I could persuade you with taking up Beagle Bone Black as a learning tool in you Embedded Systems Journey!
