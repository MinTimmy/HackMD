###### tags: `UNIX`

# Week2

##  mount / unmount

- Step1: Check the disk
```
sudo fdisk -l
```

- Step2: Key your disk and the directory
```
sudo mount [OPTION...] DEVICE_NAME DIRECTORY
```
- Step3: unmount
```
sudo unmount DIRECTORY
```
- 可以用USB實做


Mount在linux中的應用
![](https://i.imgur.com/gDRCQXm.png)

## MD5 Hash Generator

### What is an MD5 hash?

An MD5 hash is created by taking a string of an any length and encoding it into a 128-bit fingerprint. Encoding the same string using the MD5 algorithm will always result in the same 128-bit hash output. MD5 hashes are commonly used with smaller strings when storing passwords, credit card numbers or other sensitive data in databases such as the popular MySQL. This tool provides a quick and easy way to encode an MD5 hash from a simple string of up to 256 characters in length.

MD5 hashes are also used to ensure the data integrity of files. Because the MD5 hash algorithm always produces the same output for the same given input, users can compare a hash of the source file with a newly created hash of the destination file to check that it is intact and unmodified.

An MD5 hash is NOT encryption. It is simply a fingerprint of the given input. However, it is a one-way transaction and as such it is almost impossible to reverse engineer an MD5 hash to retrieve the original string.
```python=
import hashlib

# initializing string
str2hash = "1"

# encoding GeeksforGeeks using encode()
# then sending to md5()
result = hashlib.md5(str2hash.encode())

# printing the equivalent hexadecimal value.
# print("The hexadecimal equivalent of hash is : ", end="")
print(result.hexdigest())
```


