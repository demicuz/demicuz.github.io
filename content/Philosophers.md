---
title: "Philosophers"
date: "2023-01-15"
lastmod: "2023-01-15"
---

[[Multi-threaded programming]], yay!

### Useful
- [cacharle/philosophers_test](https://github.com/cacharle/philosophers_test)
- [nesvoboda/socrates](https://github.com/nesvoboda/socrates)
- [philosophers-visualizer](https://nafuka11.github.io/philosophers-visualizer/)
- [Столяров](http://www.stolyarov.info/books/pdf/osintro.pdf), с. 162
- [Рандомная проверка](https://disk.yandex.ru/i/FVeGa1GfSvxSNw)
	- [И еще](https://projects.intra.42.fr/projects/42cursus-philosophers/projects_users/2542775)
- [rabderus Notion](https://rbellero.notion.site/Philosophers-439386543ff44860870a25d6e63be109)

### To learn
- what are coroutines?
- how fast are mutexes in c when contention?
- how to debug a multi-threaded program
- producer-consumer stuff, though I don't really know if it's useful here

### Notes
It's not necessary to use a [[Mutex]] for `printf` when you have only one process running, because it's thread-safe (I think). See [[#Links]] - how to use `printf` with multiple threads. Also [[#Output control]].

`usleep` can't take values more than `10^6` because POSIX. But on most systems it will work anyway. More [here](https://stackoverflow.com/questions/12175106).

### What I've learned
Corner cases can bite you in the ass, hacky ways are dangerous.
Rounding error can be a bitch too. Remember `time_passed()`.

### Problems
##### Deadlocks
If we represent each fork with a mutex, and write an algorithm where each philosophers takes his left fork, then his right fork, all philosophers can take their left forks and get stuck. And die.

Solution - parity. For example, each philosopher with an even index can take his right fork, then his left fork. Or even simpler - the first philosopher takes right fork, then left, while others do the opposite (left, then right).

##### Starvation
As forks are not prioritized and philosophers don't speak with each other, it's not guaranteed that a fork will be taken by a philosopher who needs it most. And he can die.

**A hacky solutuion for this particular task:**
For even number of philosophers:
Make a small delay at the start of the simulation for philos with (un)even index. That's it.

For uneven number of philosophers:
Make a small delay at the start for philos with uneven index, and a delay for the last philo: `time_to_eat * 2` plus some delta, like 1 ms. And this delay should also be active for the rest of the philos after their first meal.


##### Output control
If one philosopher dies, then others shouldn't output anything to `stdout`. This would be easy to achieve with `close(1)`, but `close()` is not on the list of allowed functions, so you have to use a mutex for this.

### Functions
`pthread_create()`
Create a thread. Returns 0 on success.

`pthread_join()`
Like `wait()` for threads. Returns 0 on success.

### Bonus part
Use named semaphores, create with `sem_open()`. We're not allowed to use `sem_init()` anyway, which is required for an unnamed semaphore.

### Links
- [The Dining Philosophers Problem With Ron Swanson - adit.io](https://adit.io/posts/2013-05-11-The-Dining-Philosophers-Problem-With-Ron-Swanson.html)
- [How to use printf() in multiple threads](https://stackoverflow.com/questions/23586682)
- [pthreads - Locking mutex in one thread and unlocking it in the other](https://stackoverflow.com/questions/4608843) - it's UB
