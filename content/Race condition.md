---
title: "Race condition"
---

A race condition occurs when two or more threads can access shared data and they try to change it at the same time. Because the thread scheduling algorithm can swap between threads at any time, you don't know the order in which the threads will attempt to access the shared data. Therefore, the result of the change in data is dependent on the thread scheduling algorithm, i.e. both threads are "racing" to access/change the data.

Problems often occur when one thread does a "check-then-act" (e.g. "check" if the value is X, then "act" to do something that depends on the value being X) and another thread does something to the value in between the "check" and the "act".

### Links
- [CodeVault - What are Race Conditions?](https://www.youtube.com/watch?v=FY9livorrJI)
- [What is a race condition?](https://stackoverflow.com/questions/34510/)
- [threads - wizardzines](https://wizardzines.com/comics/threads/)
