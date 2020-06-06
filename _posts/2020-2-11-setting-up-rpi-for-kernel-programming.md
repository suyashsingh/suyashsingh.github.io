---
tite: "Configuring Raspberry Pi for Linux Kernel Development"
pretty_title: "Configuring Raspberry Pi for Linux Kernel Development"
layout: blog_post
permalink: /blog/raspberry-pi-kernel-development-setup
readTime: 15 minute
has_code: true
tag: [raspberry-pi, linux-device-driver]
description: Raspberry Pi can be configured to learn about Linux Kernel Development. Know more about configuring RPi for kernel & linux device driver development in this post.
post_intro: |
    Raspberry Pi is a Linux based single board computer. It can be configured to be used as a Linux Kernel Development or Linux Device Driver Development tool. Raspberry Pi can be confirmed easily learning tool for kernel development.
---
## 1. Why Raspberry Pi for Kernel Development?
Well this would be first question that would pop up in your head isn't it? Shouldn't I be using my safe virtual machine setup for learning kernel development. Well basically you could but you would be missing out all the fun that actual hardware has to offer you.

There are several advantages of using RPi as you kernel development tool. Firstly, you are working on a actual system with all the real hardware which won't be the case if you are using a virtual machine setup. Secondly you have access to all the tools that you would use on an Linux workstation.The thing that I like about using Raspberry Pi for kernel development is that you can do all you experiments safely.Safely in the sense all that you are putting at risk is the current installation in cases when you mess the system badly, you can get the system back to a known state using OS image backups. Now imagine the chaos that would ensue when you crash you workstation with all you data.

Kernel developers keep a sacrifical system for their development in case things went south. Here comes in Raspberry Pi, your own inexpensive sacrificial development system. Follow along for steps on how to configure a Raspberry Pi for kernel development.

## 2. Configure Raspberry Pi for Headless Mode
+ I am using **Raspberry Pi 3B+** for my kernel development setup.
+ Download **Raspbian Buster Lite** Minimal image based on Debian Buster.
The image I downloaded was released on 2020-02-13 (434 MB) and I burned it on a 32GB sd card.
Personaly I use <a href="https://www.sdcard.org/downloads/formatter/" title="download page of SD Card formatter" target="_blank">SD Card Formatter</a> and <a href="https://sourceforge.net/projects/win32diskimager/" title="download page for win32 disk imager" rel="nofollow" target="_blank">Win 32 Disk Imager</a> for creating sd cards for Raspberry Pi, you
can use any other tool you are comfortable with.
+ Add empty `ssh` file in the sd card to enable ssh on boot. This would make sure you can remotely access
your raspberry pi i.e. your development system.
+ Find IP address of the raspberry pi to gain shell access. 
You can use <a href="https://www.advanced-ip-scanner.com/" title="homepage of advanced ip scanner" target="_blank">Advanced IP Scanner</a>for finding the RPi in your network.

## 3. Setup Time Zone and Time 

This is needed as network operations need system time to be proper, eg. for installing some package. 
+ `sudo timedatectl set-timezone Asia/Kolkata` 
+ `sudo date -s "11 Feb 2020 20:00"`  

## 4. Update your distribution
+ `sudo apt-get update`  

## 5. Install Kernel Headers 
+ `sudo apt install raspberrypi-kernel-headers`

	You need the kernel headers as during kernel development process you will be including these header files.
	They need to be the ones with which the your kernel was orignally built.

## 6. Test setup by compiling Hello World Kernel Module. 
+ GCC is usually installed by default in Raspbian distributions.
+ Save the following as `hello.c` 

	```c
	#include <linux/module.h>     /* Needed by all modules */  
	#include <linux/kernel.h>     /* Needed for KERN_INFO */  
	#include <linux/init.h>       /* Needed for the macros */  

	MODULE_LICENSE("GPL");    
	MODULE_AUTHOR("Suyash Singh Bitti");  
	MODULE_DESCRIPTION("Hello World Lodable Kernel Module");  

	static int __init hello_start(void)  
	{  
	    printk(KERN_INFO "Hello World Kernel Module \n");  
	    return 0;  
	}  

	static void __exit hello_end(void)  
	{  
	    printk(KERN_INFO "Bye.!\n");  
	}  

	module_init(hello_start);  
	module_exit(hello_end);  
	```

 

+ Save the following as `Makefile`.
Make sure you are using tabs for indentation and not spaces.

	```make 
	obj-m = hello.o

	all: 
		make -C /lib/modules/$(shell uname -r)/build/ M=$(PWD) modules 
	clean: 
		make -C /lib/modules/$(shell uname -r)/build M=$(PWD) clean 
	``` 

+ Compile the module by running `make`
<img alt="d" src="{{ "/assets/images/blog-posts/compiling-driver.png" | relative_url }}" alt="compiling the hello world driver" class="img-fluid">

+ Open one more terminal and run `tail -f /var/log/kern.log` to have a look on the kernel logs. `-f` option
tells `tail` to show changes in the file at realtime. This way you won't have keep checking the logs yourself.
+ Load the kernel module: `sudo insmod hello.ko`
+ Check if your module is loaded into the kernel by running the `lsmod` command. 
+ Remove the module once you have stared it long enough.
`sudo rmmod hello` 
+ You would see kernel logs similar to this:
<img alt="d" src="{{ "/assets/images/blog-posts/checking-driver-logs.png" | relative_url }}" alt="checking kernel logs for hello world kernel module" class="img-fluid">

## 7. Install & Configure GIT
+ This step is optional. 
+ `sudo apt-get install git`
+ `git config --global user.name "Suyash"`
+ `git config --global user.email "suyash@example.com"`
+ `git config --global core.editor nano`

These steps should configure your Raspberry Pi for initial linux kernel development.

## Sources 
+ <a href="https://www.raspberrypi.org/documentation/linux/kernel/headers.md" title="raspberry pi foundation documentation  for installing kernel headers" target="_blank">Installing Kernel Header in RPi, Official Guide</a>
+ Useful Raspberry Pi forum thread for installing kernel headers using <a href="https://github.com/notro/rpi-source/wiki" titile="wiki page of rpi-source" target="_blank">rpi-source</a>. <a href="https://www.raspberrypi.org/forums/viewtopic.php?t=154749#p1095387" title="Dougie's forum post for using rpi-source" rel="ugc" target="_blank">Refer to Dougie's answer on this thread to use rpi-source</a>.
