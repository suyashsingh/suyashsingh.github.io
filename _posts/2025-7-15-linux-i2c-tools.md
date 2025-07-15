---
tite: "Exploring Linux I2C Tools"
pretty_title: "Exploring Linux I2C Tools"
layout: blog_post
readTime: 2 minute
has_code: true
tag: [linux-i2c, linux-kernel-development, learning-kernel-development, embedded-systems]
description: Exploring Linux I2C Tools
post_intro: |
    Linux I2C tools is a suite of utilities aimed at developing I2C interfaces within the Linux Kernel. Linux Kernel has a very matured I2C framework and I2C tools can help you test both your peripheral and controller driver implementations.

---

`Work In Progress`

## Overview 
I2C has a dedicated framework in the Linux Kernel. If you are interacting with this I2C framework in the Linux Kernel, it highly likely that you are exploring I2C from the peripheral point of view. However there are two sides to this story. I2C implementation can be either Controller side implementation or Peripheral side implementation.

Since most of the times we would want to use an I2C peripheral, so we will be interacting with our peripheral device via the Linux Kernel's I2C framework. I2C Tools make
make this user level interaction with the I2C peripheral device easy. I2C Tools is a bunch of I2C related utilities to read and write to your I2C peripheral device.

## I2C Tools Package
I2C Tools Package compises of serveral tools, namely:
1. i2cdetect
2. i2cdump
3. i2cget
4. i2cset

The name of the tools makes it very self-explainatory. Lets take and example to understand more about it.
Consider a scenario where you have a Beagle Bone Black board, which is having a TI AM335x SoC and a I2C based temperature sensor connected to it.
In this scenario we have the Temperature Sensor as our peripheral device. The AM335x SoC will have the I2C controller which would be controlling the I2C bus and all the transactions that happen on the I2C bus. From an end user point of view, what we are interested in is getting temperature readings from the I2C based temperature sensor. The temperature sensor will have its own communication transaction scheme. This is were I2C tools will come into play. You either have an option to write you own peripheral driver, or interact with the temperature sensor vis  tools in the I2C Tools package. Particularly we would be using i2cget and i2cset utilities of the package to interact with the peripheral device.

To summarise I2C Tools lets us interact with I2C peripherals on the command line, without writing any code. Do note that like any other tool for linux I2C Tools is a development tool or a development package, and not something you use in production. Once you have verified the desired functionality with I2C Tools you do need to write code for the peripheral. I2C Tools is just for intial development or debugguing.


## TLDR
1. I2C Tools lets you interact with I2C peripheral on the linux command line (or android)
2. I2C Tools is a development package.

## Awesome References
1. [i2c-tools github repo](https://github.com/mozilla-b2g/i2c-tools/tree/master) The repo is archived, but it is good for our use case of exploring it.

