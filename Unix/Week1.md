###### tags: `UNIX`

# Week1
## ls
```
    ls [options][file/dir]
```
- The real name: list
- Function: lists directory contents of files and directories.


| Options | Description |
| -------- | ---------- |
| -a     | List all file includinf hiden filestarting eith'.'  |
|-l|list with long format - show permissions|
|-d|list directories - with ' */' |
|-h|The human can read|

- The file permissions: -rw-r--r--
    
|Word|Maening|
|-----|------|
|-    |Document|
|d    | Directory|
|l    |soft Link|
|r    |Read    |
|w    |Write    |
|x    |Excusive    |


## rm
- Function: removes each specified file.
- The real name: remove


|Tag|Description|
|---|-----------|
|-f |ignore nonexistent files, never prompt.|
|-r |Remove the dirction|


## mkdir
```
mkdir [OPTION]... DIRECTORY...
```
- The real name: make directory

|Tag|Description|
|---|-----------|
|-p, --parents	|no error if existing, make parent directories as needed|

## cd
- The real name: change directoy

Move up one folder
```
cd ..
```

Move to the sample folder
```
cd /usr/local/sample
```
## pwd
- Function: print working director 
- The real name: print working director 
```
pwd
```
## rmdir
- Function: remove **empty** directoies
- The real name: remove empty directoies
```
rmdire directory
```
## cp
- The real nema: Copy
- Function: Copy from source to dest

```
cp [options] source dest
```
|Tag|Description|
|---|-----------|
|-r|recursive copy (including hidden files)|

## mv
- Function: mv command is used to move files and directories.
- The real name: move
```
$ mv [options] source dest
```
## rm
- The real name: remove
- rm removes each specified file. By default, it does not remove directories.
```
rm [OPTION]... FILE...
```

|Tag|Description|
|---|-----------|
|-f, --force	|ignore nonexistent files, never prompt.|
|-r, -R, --recursive	|remove directories and their contents recursively.|
## touch
The touch command is the easiest way to create new, empty files. It is also used to change the timestamps (i.e., dates and times of the most recent access and modification) on existing files and directories. 

```
touch [option] file_name(s)
```
## cat
- The real name: concatenate
- Function: reads files 
```
cat [OPTION] [FILE]...
```
## more
- Function: reads files 
```
more [OPTION] [FILE]...
```
## less
- Function: reads files 
```
less [OPTION] [FILE]...
```






