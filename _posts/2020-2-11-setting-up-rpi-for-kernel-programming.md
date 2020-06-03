---
tite: "Configuring Raspberry Pi for Linux Kernel Development"
pretty_title: "Configuring Raspberry Pi for Linux Kernel Development"
layout: blog_post
permalink: /blog/raspberry-pi-kernel-development-setup
readTime: 15 minute
has_code: true
tag: [raspberry-pi, linux-device-driver]
---

## 1. Configure Raspberry Pi for Headless Mode
+ I am using **Raspberry Pi 3B+** for my kernel development setup.
+ Download **Raspbian Buster Lite** Minimal image based on Debian Buster.
The image I downloaded was released on 2020-02-13 (434 MB) and I burned it on a 32GB sd card.
Personaly I use SD Card Formatter and Win 32 Disk Imager for creating sd cards for Raspberry Pi, you
can use any other tool you are comfortable with.
+ Add empty `ssh` file in the sd card to enable ssh on boot. This would make sure you can remotely access
your raspberry pi i.e. your development system.
+ Find IP address of the raspberry pi to gain shell access. 
You can use [Angry IP Scanner](https://www.advanced-ip-scanner.com/) for look for your RPi in your network. 

## 2. Setup Time Zone and Time 

This is needed as network operations need system time to be proper, eg. for installing some package. 
+ `sudo timedatectl set-timezone Asia/Kolkata` 
+ `sudo date -s "11 Feb 2020 20:00"`  

## 3. Update your distribution
+ `sudo apt-get update`  

## 4. Install Kernel Headers 
+ `sudo apt install raspberrypi-kernel-headers` 
You need the kernel headers as during kernel development process you will be including these header files.
They need to be the ones with which the your kernel was orignally built.

## 5. Test setup by compiling Hello World Kernel Module. 
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
+ Open one more terminal and run `tail -f /var/log/kern.log` to have a look on the kernel logs. `-f` option
tells `tail` to show changes in the file at realtime. This way you won't have keep checking the logs yourself.
+ Load the kernel module: `sudo insmod hello.ko`
+ Check if your module is loaded into the kernel by running the `lsmod` command. 
+ Remove the module once you have stared it long enough.
`sudo rmmod hello` 
+ Here is what it looks like.
<img class="img-fluid" src="https://i.imgur.com/R0J13l1.png" alt="checking that your driver is loaded into the system | Suyash Singh Bitti">

## 6. Install & Configure GIT
+ This step is optional. 
+ `sudo apt-get install git`
+ `git config --global user.name "Suyash"`
+ `git config --global user.email "suyash@example.com"`
+ `git config --global core.editor nano`

These steps should configure your Raspberry Pi for initial development.

## Sources 
+ [Installing Kenrel Header in RPi, Official Guide](https://www.raspberrypi.org/documentation/linux/kernel/headers.md)
+ Useful Raspberry Pi forum thread. [Reffering to Dougie's answer on this thread](https://www.raspberrypi.org/forums/viewtopic.php?t=154749, rpi-source can also be used), [rpi source](https://github.com/notro/rpi-source/wiki) can also
be used
