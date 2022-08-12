---
title: "How Linux Signals Work - SIGINT, SIGTERM and SIGKILL"
tags: [article, linux]
---

[original](https://www.cloudsavvyit.com/11072/linux-signals-hacks-definition-and-more/)

Software interrupts on Linux and Unix systems are made via signals. There are many different Linux signals, but a few stand out and are important to understand and know: SIGINT, SIGTERM, and SIGKILL. Here’s how they work.

## What Is a _Linux Signal_?

We all understand a red light means that we have to stop walking or driving. Similarly, in Linux and Unix systems, one can pass a signal to a running program or service to interact with it. For example, one could send a red traffic light sign to a program by simply issuing a `SIGTERM` signal.

Just like with a red traffic light, people may choose to continue to walk or drive when the light is red. Whilst that may not be a safe idea for all involved, a `SIGTERM` signal send to a process will do exactly that; the process/program may choose to ignore such a signal.

The basic Linux signals all have a number (1-30+). After a little while, a proficient Linux user will generally know one or more of these. For example, the `SIGTERM` signal matches with number 15, and signal 9 (`SIGKILL`) is likely the most the most known one as it allows one to forcefully terminate a process, unlike our `SIGTERM` red light example.

![htop displaying possible program signals](https://www.cloudsavvyit.com/p/uploads/2021/05/7afbb160-1.png?trim=1,1&bg-color=000&pad=1,1)

Here we see the main screen of `htop` (you can install this handy utility by typing `sudo apt install htop` on Ubuntu/Mint, or `sudo yum install htop` on RedHat/Centos/Fedora) with a number of termination and other signals (lower in the list; there are 37 in total) which can be sent to a process previously selected on the right. One can select a process by pressing the cursor up/down and then send a signal by using F9.

## SIGKILL & SIGTERM

Whilst the name may sound a little sinister, the common Linux lingo for process termination is that one ‘kills’ a process. Generally speaking, we will only want to terminate a process with a `-9` (`SIGKILL`) signal if such a process/program is hanging. Note that whenever we speak of process or program, the words can be interchanged at will. Basically, a process is any running program (or service) that has been given a _PID_ (a process identifier).

Let’s look at an example of terminating a running background process by using a `SIGKILL` signal to the running process. Note that as explained `SIGKILL` is rather destructive and will terminate the process no matter what the process would like to do with the signal. A number of signals can be captured and redirected by the process, whereas others cannot.

![Sending SIGKILL to a sleep process running in the background](https://www.cloudsavvyit.com/p/uploads/2021/05/586e508f-1.png?trim=1,1&bg-color=000&pad=1,1)

Here we started a `sleep 1800` in the background (using `&` at the end of the command), which was started as the first (`[1]`) background process with `PID 574660`. We subsequently killed that background process using `kill -9 574660`, where the `-9` stands for `SIGKILL`.

While the process is terminated immediately, we do not see the termination message (background process `1` killed, i.e., `[1]+ Killed`) as the command prompt returns before the message is displayed, i.e., returning the command line was a faster operation then the process termination, or similar.

We check the process list by grepping for the PID `ps -ef | grep 574660`. Whilst there is some output, the output shown is only for our running `grep` command; the `sleep` process has already been terminated.

Let’s evaluate the same with `SIGTERM`, i.e. `kill -15 ${PID}` where `${PID}` is the process we want to terminate.

![Sending SIGTERM to a sleep process running in the background](https://www.cloudsavvyit.com/p/uploads/2021/05/59b2900a-2.png?trim=1,1&bg-color=000&pad=1,1)

We had to press enter to trigger/show the termination message (as explained above). We can see that the program terminated correctly again. However, this time, while invisible for this particular example (read on!), internally inside the `sleep` program code, things went a little different.

In this case (using `-15` i.e. `SIGTERM` to terminate the process), the `sleep` process was notified and had the opportunity to internally handle the signal. It could subsequently respond by self-terminating, by ignoring the signal, or by any other action as developed into the code. We can also prove this to be true by checking the exit signal and/or output:

![The difference in output and exit codes depending on the signal sent](https://www.cloudsavvyit.com/p/uploads/2021/05/9eb60bc8-1.png?trim=1,1&bg-color=000&pad=1,1)

Here we started the process `sleep 2000` twice, and then used another shell/terminal session to terminate the program. The first time, we used `kill -9` and the second time we used `kill -15` to stop the `sleep` process.

We immediately notice how the output returns `Killed` in the first (`kill -9` action) instance. For the second attempt (using `kill -15`), we see the output `Terminated` instead; the program self-terminated. Subsequent to the respective terminations we also checked the exit signals, and found that the exit codes were different.

Why is this important? Consider larger programs; in this instance, we were just terminating a simple `sleep` command. There was no data being handled, no traffic being sent back/forth, etc. But what would happen if we sent a `kill -9` command to our database server (this would generally speaking require sudo/root-level privileges)?

It would trigger the database to go into crash recovery mode the next time it starts up because, as far as the database software knows, all that happened was “was there” followed by “nothing.” In other words, it crashed. If we had instead issued a `kill -15` command, the database software could have done a controlled shutdown, for example, by first blocking new users from connecting, then disconnecting/terminating existing users, then finish writing data, etc. before finally self-terminating.

## Sending Linux Signals with Keyboard Sequences

Did you know that whenever you sent a `CTRL+C` key sequence to a running program, for example in a terminal, that instead a `SIGINT` is sent? Let’s step back to our trusted `sleep` command and test this:

![A sleep process interrupted by a SIGINT signal sent via a CTRL+C key sequence](https://www.cloudsavvyit.com/p/uploads/2021/05/c00b5755.png?trim=1,1&bg-color=000&pad=1,1)

Here we started `sleep` again, and then pressed the keyboard combination `CTRL+C`. The program terminated, or better _was interrupted_ by the `SIGINT` signal that was sent. We request the exit code and confirm that once again the exit code is different from the previous signals.

Note that this exit code, for sleep, will always be matched to the signal sent, though potentially not all signals may be covered. In other words, when using `CTRL+C` at the command line the exit code will always be `130`, `137` when killed with `kill -9`, and `143` when `kill -15` was used.

You can test exit codes for commands by querying the `$?` variable, which holds the exit code of the previous command (as long as you have not commenced a new command). Knowing the exit code of a given command in a particular situation, and/or as the result of a particular signal sent to that command, helps when scripting solutions that handle other processes, etc. (which is the case for many shell scripts, especially when managing servers or automated environments).

Another often-used keyboard sequence is `CTRL+Z`. This will sent a `SIGTSTP` signal, a `suspend` signal which immediately places a process in suspension until (for example) a `'fg'` command is issued for the same process which will bring it back to the foreground.

To learn more about process management, see [Bash Process Termination Hacks](https://www.cloudsavvyit.com/9290/bash-process-termination-hacks/).

## Wrapping up

In this article, we looked at the most important Linux signals and how we may practically use them in a Linux or Unix environment. Knowing the basic Linux signals aids one with daily Linux use and management, for example, when a process is hanging and needs to be terminated with `kill -9`. In a future article, we may look at capturing a signal using the `trap` command from inside a Bash script, allowing one to define a custom procedure to be executed when such a signal is issued.

If you enjoyed reading this article, have a look at our Bash automation series starting at [Bash Automation & Scripting Basics](https://www.cloudsavvyit.com/9676/bash-automation-scripting-basics-part-1/). In the third article in that series, we also discuss background process management, touched on earlier in this article.
