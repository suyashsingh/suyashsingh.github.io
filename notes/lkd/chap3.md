---
layout: default
---

# Chapter 3 (Scribbles)
1. Process
2. How is process relates to an operating system. How is it important to the ker
nel.
3. Definition of process. Resources they have.
4. Threads - resources, scheduling
5. Virtualization provided by processes - Illusions
6. Virtual Memory
7. Threads
  + sharing virtual memory abstraction
  + single virtual processor
8. Two processes sharing same resources
9. How processes come into life
  + parent vs child
  + fork system call returns from kernel twice - brief life cycle of a process
  + exit()
  + wait4() system call - special zombie state
  + task
10.
  + What is a task list
  + Definition of process descriptor
  + infor contained in the process descriptor
11.
  + Storage of struct `task_struct` at end / bottom of kernel stack. Why?
  + struct `thread_info` - why?
12. `pid_t`, its storage in process descriptor
13. Max value for `pid_t` - controlling it
14. Importance of the max value.
15. pid wrap around.
16. `/proc/sys/kernel/pid_max`
17. How are tasks refferences in kernel code.
18. `current` macro
19. Efficient access of `thread_info` structure
20. How is location of current calculated on x86 platforms
21. `current_thread_info`
22. Accessing `task_struct` in PPC
23. State field of the process descriptor
24. five flags
25. `TASK_RUNNING` - user space
26. Diagram
27. `set_task_state` (task state)
28. How is `set_task_state` different from `task->state = state`
29. `set_current_state(state)` - <linux/sched.h>
30. Kernel executing on behalf of proces.
31. Well defined interfaces into the kernel.
32. process family tree - how is relation stores on process descriptor
33. init process - boot process relation
34. siblings, children, parent field
35. process descriptor of init task - statically allocated.
36. Iterating over all child processes
37. moving back till init
38. Iteratin all the tasks in the system using list_entry
39. `next_task(task)`, `previous_task(task)`
40. `for_each_process(task)`
41. 2 separate steps
42. what happens on fork
43. What happens on exec()
44. Definition of cow
45. How is cow good.
46. overhead incurred while fork()
47. Implementation of fork(), what it does, what all functions it calls
48. why is child woken up deliberately after fork()
49. `vfork()` system call, how it works
50. `mm_release()` function
51. what threads do - concurrent programming, parallelism
52. what resources are shared
53. threads and clone system calls
54. how is fork implemented
55. how is vfork impremented
56. how clone flags come into play
57. what are kernel threads
58. difference between kernel threads and normal processes - `mm pointer`
59. similarities between kenel threads and normal processes
60. flush & ksoftirqd tasks
61. `kthreads`
  + how are they created
  + `kthreadd` kernel process
  + `kthread_create`, `clone()` system call is used
  + `wake_up_process()`
  + `kthread_run` macro
  + stopping kernel thread - `do_exit()`, `kthread_stop()`
62. Process termination
63. `do_exit()` what all it does
64. Task state if a process in exit state
65. Memory occupied by a task in exit state
66. Significance of `mm_struct`
67. Deallocation of task_struct - when is it done
68. `wait()` family of functions
69. `release_task()`, `_exit_signal()`, `_unhash_process()`, `_detach_pid()` all
the chain of function calls in `release_task*()`
70. Dilema of parentless task
71. Reparenting to other processes in thread group or init process
72. Reparenting of ptraces process
