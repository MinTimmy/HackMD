###### tags: `UNIX`

# GNU Coreutils
## fmt
by default with no option used format all the words present in the given file in a single line.
```
$cat kt.txt
$ cat kt.txt
hello
everyone.
Have
a
nice 
day.

/* fmt by default puts all words 
   in a single line and prints on
   stdout. */
$fmt kt.txt
hello everyone. Have a nice day.
```

## pr
In Linux/Unix pr command is used to prepare a file for printing by adding suitable footers, headers, and the formatted text. pr command actually adds 5 lines of margin both at the top and bottom of the page.  The header part shows the date and time of the last modification of the file with the file name and the page number. 

```
$cat abc
1
2
3
4
5
6
7
8
9
$pr -3 abc
2020-11-06 21:40                        a                         Page 1

1			4			7
2			5			8
3			6			9
```


## fold
fold command in Linux wraps each line in an input file to fit a specified width and prints it to the standard output. By default, it wraps lines at a maximum width of 80 columns but this is configurable. To fold input using the fold command pass a file or standard input to the command.

* -s : This option is used to break the lines on spaces so that words are not broken. If a segment of the line contains a blank character within the first width column positions, break the line after the last such blank character meeting the width constraints. 
```
$cat a
A wiki (/ˈwɪki/ (About this soundlisten) WIK-ee) is a hypertext publication co
llaboratively edited and managed by its own audience directly using a web browse
r. A typical wiki contains multiple pages for the subjects or scope of the proje
ct and may be either open to the public or limited to use within an organization
 for maintaining its internal knowledge base. 
 
$fold -40 -s a
A wiki (/ˈwɪki/ (About this 
soundlisten) WIK-ee) is a hypertext 
publication collaboratively edited and 
managed by its own audience directly 
using a web browser. A typical wiki 
contains multiple pages for the 
subjects or scope of the project and 
may be either open to the public or 
limited to use within an organization 
for maintaining its internal knowledge 
base. 

```

## head: Output the first part of files
It is the complementary of Tail command. The head command, as the name implies, print the top N number of data of the given input. By default, it prints the first **10** lines of the specified files. If more than one file name is provided then data from each file is preceded by its file name.
```
$ cat state.txt
Andhra Pradesh
Arunachal Pradesh
Assam
Bihar
Chhattisgarh
Goa
Gujarat
Haryana
Himachal Pradesh
Jammu and Kashmir
Jharkhand
Karnataka
Kerala
Madhya Pradesh
Maharashtra
Manipur
Meghalaya
Mizoram
Nagaland
Odisha
Punjab
Rajasthan
Sikkim
Tamil Nadu
Telangana
Tripura
Uttar Pradesh
Uttarakhand
West Bengal

$ head state.txt
Andhra Pradesh
Arunachal Pradesh
Assam
Bihar
Chhattisgarh
Goa
Gujarat
Haryana
Himachal Pradesh
Jammu and Kashmir
```
## tail: Output the last part of files
It is the complementary of head command.The tail command, as the name implies, print the last N number of data of the given input. By default it prints the last 10 lines of the specified files. If more than one file name is provided then data from each file is precedes by its file name. 
```
$ cat state.txt
Andhra Pradesh
Arunachal Pradesh
Assam
Bihar
Chhattisgarh
Goa
Gujarat
Haryana
Himachal Pradesh
Jammu and Kashmir
Jharkhand
Karnataka
Kerala
Madhya Pradesh
Maharashtra
Manipur
Meghalaya
Mizoram
Nagaland
Odisha
Punjab
Rajasthan
Sikkim
Tamil Nadu
Telangana
Tripura
Uttar Pradesh
Uttarakhand
West Bengal

$ tail state.txt
Odisha
Punjab
Rajasthan
Sikkim
Tamil Nadu
Telangana
Tripura
Uttar Pradesh
Uttarakhand
West Bengal
```

## split: Split a file into pieces.
Split command in Linux is used to split large files into smaller files. It splits the files into 1000 lines per file(by default) and even allows users to change the number of lines as per requirement.

```
$ls
a
$cat a
1
2
3
4
5
6
7
8
9
$split -l 4 a split_file
$ls
a split_fileaa  split_fileab  split_fileac
$cat split_fileaa 
1
2
3
4
$cat split_fileab
5
6
7
8
$cat split_fileac
9
```

## csplit: Split a file into context-determined pieces
The csplit command is used to split any file into many parts as required by the user. The parts are determined by context lines. Output pieces of FILE separated by PATTERN(s) to files ‘xx00’, ‘xx01’, …, and output byte counts of each piece to standard output.

* -f, –Prefix: It use PREFIX in place of ‘xx’. 
```
$ls
a
$cat a
1
2
3
4
5
6
7
8
9
$csplit -f qwe a 2
$ls
a qwe00 qwe01
$cat qwe00
1
$cat qwe01
2
3
4
5
6
7
8
9
```

## wc: Print newline, word, and byte counts