---
tite: "Beagle Bone Black Setup"
pretty_title: "Setting Up Beagle Bone Black"
layout: blog_post
readTime: 10 minute
tag: [beagle-bone-black, bbb, embedded-systems]
description: This post is about setting up a beagle bone black board for its first boot.
post_intro: |
    Hey there!

	In this post we would be looking on how to setup Beagle Bone Black Rev. C board for the maiden boot. The initial steps would be same irrespective of what you are trying to do with your Beagle Bone Black. Be it learning Embedded Linux or just are exploring beagle board for generic usage such a connecting some sensors and using them via python or C. You need to have a basic hardware setup to get stated. This post help you get up and running as quickly as possible with your Beagle Board.
Before diving hands on into the configuring your board let's take some time to get an overview of what has to be done.

---

`Work In Progress`

## Overview 
Beagle Bone is an open source Single Board Computer a.k.a SBC. It runs Linux and lets you interact with the onboard hardware via the interface exposed by a Linux system. So if you have to setup a Beagle Bone Black you obviously need to get Linux installed somehow onto the board. Now the question arises from where to get the Linux and how to install it. Since Beagle Bone is kind of a specialized board you can’t just install Ubuntu or Fedora or any common distribution directly onto it, it won't be supported. You would have to look for a flavor of Linux OS customized / built sepecifically for Beagle Bone. 

Apart from the OS, since it is a electronic device it naturally needs power to run. You can use the USB cable included in the box or you can use a 5V power adapter to power it up. In most cases the USB cable should be just fine. Now with the board power supply and the OS in place(we will get to it… for now follow along!)   we can technically boot it and it would run. So at this point when you power the board it would boot and you would be able to see the on board led's flashing. But you won't be able to see any logs and that’s a bummer. So for having a peek into what's going on in the boot process we would need a Serial Cable. That’s it, all the setup you need in place to boot a Beagle Bone Black board.

> Note:
> You might be in either of two categories:
> 	1. You bought the board recently and you are the first one unboxing it.
>	2. You had the board already with you, but you don’t know what's the state of the board.
> We will look into both of these scenarios. The first scenario is definitely very easy, in the second stage you would have a lot of learning :).

So in a nutshell you would need the following components:

## Hardware Required
1. Beagle Bone Black Rev. C Board
2. The USB cable that came with the board. It’s a Micro USB to USB cable.
3. USB to Serial Cable: This also can be seen as an optional component. But its good to have. If your board is new when the Linux boot on Beagle Board is completed a mass storage device enumerated. This was  you know that your board is booting fine.
4. Power Adapter 5V 1A or 2A. This is optional, if you are not connecting extra hardware to the board powering it via the USB cable from a pc should be fine. I recommend you to start with just the USB cable to check you board is working fine and then move on to power supply. If you have a multimeter you can check the voltage at the DC barrel jack. It should be slightly more than 5V e.g. around 5.3Volts instead of 5V. This is good, since with the board connected the voltage would drop slightly. If you see a voltage less than 5V even without of the board, you should change the cable.
	
## Software Tools
1. Serial Terminal Software: On windows you can use: Tera Term, Putty, Mobaxterm. I recommend using Tera Term. On Linux you can use minicom. Make sure you configure minicom first. Usually minicom will have Hardware flow control enabled by default. If you are able to see the logs but you can't type anything, check if Hardware flow control is enabled. It should be off.

2. SSH Software:Maxterm is an excellent choice for SSH client. You can however do SSH via the windows command prompt as well, it supports SSH. If you are using a Linux host you don’t need to install anything. Almost all the Linux distributions have SSH client installed by default.

