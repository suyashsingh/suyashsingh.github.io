---
tite: "Beagle Bone Black Setup"
pretty_title: "Setting Up Beagle Bone Black"
layout: blog_post
readTime: 10 minute
tag: [beagle-bone-black, bbb, embedded-systems]
description: This post is about setting up a beagle bone black board for its first boot.
post_intro: |
 Hey there! In this post we will be looking at how to setup Beagle Bone Black(RevC) board for it first boot. Wether you are focused on Hands-on Embedded Linux or are exploring Beagle Bone for you next projct, the initial steps remain the same. You will need to setup a bare minimum hardware setup to get stated. This guide is going to help you get up and running as quickly as possible. Before diving in to the morbid details, let's take some time to get an overview of what has to be done.

---

`Work In Progress`

## Overview 
Beagle Bone is an Open source Single Board Computer or an SBC. It runs Linux and lets you interact with various SoC interfaces via the onboard hardware. If you have to setup a Beagle Bone Black you obviously need to get Linux installed somehow onto the board. Now the question arises from where to get the Linux and how to install it. Since Beagle Bone is kind of a specialized board you can't just install Ubuntu or Fedora or any common distribution directly onto it, it won't be supported. You would have to look for a flavor of Linux OS customized / built sepecifically for Beagle Bone. 

Apart from the Operating System, since it's electronic device it naturally needs power to run. You can use the USB cable included in the box or you can use a 5V power adapter to power it up. In most cases the USB cable should be fine. Now with the board power supply and the OS in place(we will get to it, for now follow along!) we can technically boot it. So at this point when you power the board it would boot and you would be able to see the on board led's flashing. But you won't be able to see any logs and that's a bummer. So for having a peek into what's going on in the boot process we would need a Serial Cable. That's it, all the setup you need in place to boot a Beagle Bone Black board.

<div class="alert alert-info" role="alert">
<b>Note: </b>You might be in either of two categories:
<ol>
<li>You bought the board recently and you are the first one unboxing it.</li>
<li>You had the board already with you, but you don't know what's the state of the board.</li>
We will look into both of these scenarios. The first scenario is definitely very easy, in the second case you would have a lot of learning :)
</ol>
</div>
Now that we have some idea, lets dig in...

## Hardware Required
1. Beagle Bone Black Rev. C Board
2. The USB cable that came with the board. It's a Micro USB to USB cable.
3. USB to Serial Cable: This can be seen as an optional component. But it's good to have. With a fresh board as upon Linux boot completion a mass storage device enumerated.
4. Power Adapter 5V 1A or 2A. This is optional, if you are not connecting extra hardware to the board powering it via the USB cable from a PC is A-Okay! I recommend you to start with just the USB cable to check you board is working fine and then move on to power supply. If you have a multimeter you can check the voltage at the DC barrel jack. It should be slightly more than 5V e.g. around 5.3V. This is good, as there would be a slight voltage drop when the bord draws power from it. If you see a voltage less than 5V even without of the board, you should change your power supply.

	<div class="alert alert-info" role="alert">
	<b>Note: </b> Low voltage might have erratic effects on the board. If you are seeing your board going nuts, check the input voltage.
	</div>

## Software Tools
1. Serial Terminal Software: On windows you can use: Tera Term, Putty, Mobaxterm. I recommend using Tera Term. On Linux you can use minicom. Make sure you configure minicom first. Usually minicom will have Hardware flow control enabled by default. If you are able to see the logs but you can't type anything, check if Hardware flow control is enabled. It should be off.

	<div class="alert alert-info" role="alert">
	<b>Note: </b>Minicom has hardware flow control turned on by default, turn it off. If you are able to see the logs but can't type anything on the board, check hardware flow control settings.
	<br/>
	<b>Note: </b>Windows command prompt can also be used. Use ssh@ip-address at the cmd prompt
	</div>

2. SSH Software:Mobaxterm is an excellent choice for SSH client. If you are using a Linux host, a SSH client might be already installed.



