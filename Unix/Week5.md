###### tags: `UNIX`

# Week5

## Process VS Program(4.1.2.1)
| Parameter | Process | Program |
| -------- | -------- | -------- |
| Definition    | An executing part of a program is called a process.     | A program is a group of ordered operations to achieve a programming goal.     |
|Nature| 	The process is an instance of the program being executing.| 	The nature of the program is passive, so it's unlikely to do to anything until it gets executed.|
|Resource management |	The resource requirement is quite high in case of a process.| 	The program only needs memory for storage.|
|Overheads 	|Processes have considerable overhead. |	No significant overhead cost.|
|Lifespan |	The process has a shorter and very limited lifespan as it gets terminated after the completion of the task. |	A program has a longer lifespan as it is stored in the memory until it is not manually deleted.|
|Creation |	New processes require duplication of the parent process. |	No such duplication is needed.|
|Required Process |	Process holds resources like CPU, memory address, disk, I/O, etc. |	The program is stored on disk in some file and does not require any other resources.|
|Entity type |	A process is a dynamic or active entity. 	|A program is a passive or static entity.|
|Contain |	A process contains many resources like a memory address, disk, printer, etc. |	A program needs memory space on disk to store all instructions.|

## CPU & Memory & Disk()
![](https://i.imgur.com/jOawXDE.png)


## CPU Operation: 
fetch, decode, execute, write
## Thread (computing)
In computer science, a thread of execution is the smallest sequence of programmed instructions that can be managed independently by a scheduler, which is typically a part of the operating system.[1] The implementation of threads and processes differs between operating systems, but in most cases a thread is a component of a process. Multiple threads can exist within one process, executing concurrently and sharing resources such as memory, while different processes do not share these resources. In particular, the threads of a process share its executable code and the values of its dynamically allocated variables and non-thread-local global variables at any given time.




## process identifier(PID)(4.1.5)
In computing, the process identifier (a.k.a. process ID or PID) is a number used by most operating system kernels—such as those of Unix, macOS and Windows—to uniquely identify an active process. This number may be used as a parameter in various function calls, allowing processes to be manipulated, such as adjusting the process's priority or killing it altogether. 

## Fork-and-exec mechanism(4.1.5)
A new process is created because an existing process makes an exact copy of itself. This child process has thesame environment as its parent, only the process ID number is different. This procedure is called forking.After the forking process, the address space of the child process is overwritten with the new process data. Thisis done through an exec call to the system.The fork-and-exec mechanism thus switches an old command with a new, while the environment in which thenew program is executed remains the same, including configuration of input and output devices, environmentvariables and priority. This mechanism is used to create all UNIX processes, so it also applies to the Linuxoperating system. Even the first process, init, with process ID 1, is forked during the boot procedure in theso-called bootstrapping procedure.This scheme illustrates the fork-and-exec mechanism. The process ID changes after the fork procedure:
![](https://i.imgur.com/QocyXeH.png)

## Special Modes(3.4.2.5)
```
xst rwx rwx rwx
```
### special execute(x):

有一款遊戲 rogue ，這遊戲開放所有人遊玩，遊玩結束後會把成績寫到 score 裡頭，所以權限會寫成
```
000 rwxrwxrwx klim rogue
000 rw-rw-rw- klim score
```
但這裡出現一個問題，有些玩家會作弊，直接進入 score 修改成績，會造成不公平，所以要使用 special execute(x) ，來解決這個問題，所以權限會寫成
```
100 rwxrwxrwx klim rogue
000 rw-rw-rw- klim score
```
當玩家(timmy)執行 rogue，他的基本資料會改變
||real user(rusr)|effective user|
|-----|---------|--------------|
|讀取rogue前|timmy|timmy|
|讀取rogue後|timmy|root|
這樣 timmy 就不能直接更改 score 裡頭的資料，一定要先玩 rogue 才能更改 score 的資料。

* real user id: is who you really are (the one who owns the process)
* effective user id: is what the operating system looks at to make a decision whether or not you are allowed to do something (most of the time, there are some exceptions)

etc/shadow
etc/passwd
### setuid/gid(s)
### Sticky bit mode(t)
After execution of a job, the command is kept in the system memory. Originally this was a feature used a lot to save memory: big jobs are loaded into memory only once. But these daysmemory is inexpensive and there are better techniques to manage it, so it is not used anymore for itsoptimizing capabilities on single files. When applied to an entire directory, however, the sticky bit hasa different meaning. In that case, a user can only change files in this directory when she is the userowner of the file or when the file has appropriate permissions. This feature is used on directories like/var/tmp, that have to be accessible for everyone, but where it is not appropriate for users to change or delete each other's data. The sticky bit is indicated by a t at the end of the file permission

```
chmod +t test
```