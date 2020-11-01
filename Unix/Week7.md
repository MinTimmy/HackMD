###### tags: `UNIX`

# Week 7

## 一般知識
* ty(終端設備的統稱):
tty一詞源於Teletypes，或者teletypewriters，原來指的是電傳打字機，是通過串行線用打印機鍵盤通過閱讀和發送信息的東西，後來這東西被鍵盤與顯示器取代，所以現在叫終端比較合適。
終端是一種字符型設備，它有多種類型，通常使用tty來簡稱各種類型的終端設備。


* pty（虛擬終端):
但是如果我們遠程telnet到主機或使用xterm時不也需要一個終端交互麼？是的，這就是虛擬終端pty(pseudo-tty)

## Process
Controlling processes


| (part of) command	 | Meaning | 
| -------- | -------- | 
| regular_command     | Runs this command in the foreground.     | 
|command &	|Run this command in the background (release the terminal)|
|jobs	|Show commands running in the background.|
|Ctrl+Z|	Suspend (stop, but not quit) a process running in the foreground (suspend).|
|Ctrl+C	|Interrupt (terminate and quit) a process running in the foreground.|
|%n	|Every process running in the background gets a number assigned to it. By using the % expression a job can be referred to using its number, for instance fg %2.|
|bg	|Reactivate a suspended program in the background.|
|fg	|Puts the job back in the foreground.|
|kill	|End a process (also see Shell Builtin Commands in the Info pages of bash)|

1. report a snapshot of the current processes.
```
ps [options]
```
------------------------------------------------
2. find username from the current process
```
ps -ef | grep username 
```
------------------------------------------------

3. kill - send a signal to a process
```
kill [options] <pid> [...]
```
------------------------------------------------

4. Interrupt 19232
```
kill 19232
```
------------------------------------------------

5. Interrupt 19232 and it can not ignore.
```
kill -9 19232
```
------------------------------------------------

6. 外部執行檔的路徑，如 ls, mvhyu, mkdir.......
```
echo $PATH
```



## at 

1. When you’re done entering the commands, press Ctrl-D to exit the prompt and save the
```
at [runtime]
```
------------------------------------------------

2. The output will list all jobs, one per line. Each line includes the job number, date, time, queue letter, and username.
```
atq
```
```
at -l
```

------------------------------------------------
3. To remove a pending job
```
atrm [ job number]
```

## crontab
Chech the correct crontab time
https://crontab.guru/

---------------------------
show the crontab
```
crontab -l
```
-----------------------------
Edit the crontab
```
crontab -e
```