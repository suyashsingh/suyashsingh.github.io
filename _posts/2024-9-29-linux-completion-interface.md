---
tite: "Linux Completion Interface"
pretty_title: "Linux Completion Interface"
layout: blog_post
readTime: 10 minute
has_code: true
tag: [learning-kernel-development, embedded-systems]
description: Gentle introduction to Linux Completion Interface.
post_intro: |
    Linux Completion interface lets us wait for some event in our kernel driver code. Completion interface greatly simplifies the code where barrier like functionality is required.

---

`Work In Progress`

## Overview 
Completions in Linux make it easy for kernel programmers / driver developers to add barrier like functionality. Often times we are required to wait in our driver code for some event to occur. Linux completion make that a breeze!

## What is Completion
As you would have guessed, completion is used for waiting for some event to be complete in our driver. Think of it similar to a barrier. Completion are built on top of wait queue. There are two parts of the completion interface. First one is the code path that is waiting for something to happen. The other part being the one that signals that it has been done.

One thing to note is that since the completion is based on wait queue it will sleep. So the part that is waiting for a completion should not be done from atomic or interrupt context. To reiterate the waiting part cannot be in a context that cannot sleep. The other part, which is the signaling part can be in an atomic context.

To give an example if our driver is waiting for data to be flushed from hardware FIFO on a  completion. This waiting part must not be in an atomic context. In the same example say there is an interrupt handler, which is called when the data is flushed out from the FIFO, this part can signal the completion that the data is flushed out. And the signaling part being in ISR is perfectly fine.

**Key: waiting part of the completion uses wait-queue, hence it will sleep.**

`struct completion` represents a completion in liunx. It is defined as [follows](https://elixir.bootlin.com/linux/v6.11/source/include/linux/completion.h):
```c
/*
 * include/linux/completion.h
 * https://elixir.bootlin.com/linux/v6.11/source/include/linux/completion.h
 */
struct completion {
	unsigned int done;
	struct swait_queue_head wait;
};
```

## TLDR
1. Linux Completion interface is based on wait queues
2. Waiting part can only be in process context as it can sleep
3. Signaling part can be in any context: atomic context, process context.

## Awesome References
1. I found the kernel documentation to be really good. [Completion Kernel Documentation](https://www.kernel.org/doc/Documentation/scheduler/completion.txt)

2. Linux Completion Header File: Do a skim read. See the actual completion stucture and the completion API's. [Completion Header: completion.h](https://elixir.bootlin.com/linux/v6.11/source/include/linux/completion.h)
