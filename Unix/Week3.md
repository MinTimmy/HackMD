###### tags: `UNIX`

# Week3

## Inode
![](https://i.imgur.com/wExJQSL.jpg)
### inode
The inode (index node) is a data structure in a Unix-style file system that describes a file-system object such as a file or a directory. Each inode stores the attributes and disk block locations of the object's data. File-system object attributes may include metadata (times of last change, access, modification), as well as owner and permission data..
### attributes
* Device ID (this identifies the device containing the file; that is, the scope of uniqueness of the serial number).
* File serial numbers.
* The file mode which determines the file type and how the file's owner, its group, and others can access the file.
* A link count telling how many hard links point to the inode.
* The User ID of the file's owner.
* The Group ID of the file.
* The device ID of the file if it is a device file.
* The size of the file in bytes.
* Timestamps telling when the inode itself was last modified (ctime, inode change time), the file content last modified (mtime, modification time), and last accessed (atime, access time).
* The preferred I/O block size.
* The number of blocks allocated to this file.

## Metadata
### metadata
Metadata is "data that provides information about other data". In other words, it is "data about data". Many distinct types of metadata exist, including descriptive metadata, structural metadata, administrative metadata, reference metadata and statistical metadata. 

## Link
```
ln [OPTION]... [-T] TARGET LINK_NAME   (1st form)
ln [OPTION]... TARGET... DIRECTORY     (2nd form)
```
**PS: LINKNAME & DIRECTORY should not exit before linking.**

### Function
The ln command is used to create links between files.

### Links Types
- Hard links: You can think a hard link as an additional name for an existing file. Hard links are associating two or more file names with the same inode . You can create one or more hard links for a single file. Hard links cannot be created for directories and files on a different filesystem or partition.The inode of two file will same.

- Soft links(symbolic link): A soft link is something like a shortcut in Windows. It is an indirect pointer to a file or directory. Unlike a hard link, a symbolic link can point to a file or a directory on a different filesystem or partition. The inode of two file will not same.


## df
```
df -ih
```
### Real name
Display file system,
### Function
Display file system and inode.



## stat
```
stat [FILENAME]
```

### Real name
status

### Function
Display other information.


