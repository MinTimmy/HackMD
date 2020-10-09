###### tags: `UNIX`

# Week4

## chmod
```
chmod [options] [permissions] [filename]
```
### Description

On Unix-like operating systems, a set of flags associated with each file determines who can access that file, and how they can access it. These flags are called file permissions or modes, as in "mode of access." The command name chmod stands for "change mode." It restricts the way a file can be accessed.

### Access mode codes


| Code | Meaning | 
| -------- | -------- | 
| 0 or - | The access right that is supposed to be on this place is not granted.| 
|4 or r|read access is granted to the user category defined in this place|
|2 or w|write permission is granted to the user category defined in this place|
|1 or x|execute permission is granted to the user category defined in this place|

### User group codes
|Code|Meaning|
|----|----|
|u|user permissions|
|g|group permissions|
|o|permissions for others|

### File protection with chmod
|Command|Code|Meaning|
|-------|----|------|
|chmod 400 file	|-r--------|To protect a file against accidental overwriting.|
|chmod 500 directory|-r-x------|	To protect yourself from accidentally removing, renaming or moving files from this directory.
|chmod 600 file	|-rw-------|A private file only changeable by the user who entered this command.
|chmod 644 file	|-rw-r--r--|A publicly readable file that can only be changed by the issuing user.
|chmod 660 file|-rw-rw----|Users belonging to your group can change this file, others don't have any access to it at all.
|chmod 700 file|-rwx------|Protects a file against any access from other users, while the issuing user still has full access.
|chmod 755 directory	|-rwxr-xr-x|For files that should be readable and executable by others, but only changeable by the issuing user.
|chmod 775 file	|-rwxrwxr-x|Standard file sharing mode for a group.
|chmod 777 file	|-rwxrwxrwx|Everybody can do everything to this file.
	
    
### Change file mode
r--r-----
```
chmod ug+w [FILENAME]
```
rw-rw----
```
chmod o+rwx,g-w [FILENAME]
```
rw-r--rwx

## grep

## find



