###### tags: `UNIX`


# Sell Programming


## Variable 
```shell=
name=timmy
```
變數宣告等號左右不可有空格
```shell=
$name
```
從變數取值要加$符號


## Read 
```shell=
if [ $# -eq 1 ]; then 
  pat=$1
else
  echo -n "Pat is: "
  read pat
fi
echo $pat
```

$# 使用者輸入的參數數量
read pat: 使用者輸入資料

## Case
```shell=
#!/bin/bash

pat=${1-timmy}

case `uname` in 
    "Linux"|"SunOS") 
        cmd="ps -ef"
        ;;
    *)
        cmd="ps augx"
        ;;
esac

$cmd | grep $pat

```

`` 執行反引號的命令

*)： case 的 default 值

;;：一個 case 的結束符號


## For
```shell=
#!/bin/bash

echo "Number of argument is : $#"

i=1
for  arg in $*; do
  printf "arg[%d] = %s\n" $i $arg
  i=`expr $i + 1`
done

```
```
printf "arg[%d] = %s\n" $i $arg 
```
%d 代替整數型態
%s 代替字串型態
```
i=`expr $i + 1`
```
等同 i++

## if
```shell=
NUM1=31
NUM2=5
if [ "$NUM1" -gt "$NUM2" ]
then
  echo "$NUM1 is greater than $NUM2"
else
  echo "$NUM1 is less than $NUM2"
fi
```
val1 -eq val2 Returns true if the values are equal
val1 -ne val2 Returns true if the values are not equal
val1 -gt val2 Returns true if val1 is greater than val2
val1 -ge val2 Returns true if val1 is greater than or equal to val2
val1 -lt val2 Returns true if val1 is less than val2
val1 -le val2 Returns true if val1 is less than or equal to val2

## Sum

```shell=
#!/bin/bash

echo "Number of argument is : $#"

i=0; sum=0
for  arg in $*; do
  printf "arg[%2d] = %s\n" $i $arg
  i=`expr $i + 1`
  sum=`expr $sum + $arg`
done

echo "The sum is $sum"
```

```
$*
```
代表所有使用者所輸入的數字

## bc

```
#!/bin/bash

echo "Number of argument is : $#"

i=0; str=""
for  arg in $*; do
  printf "arg[%2d] = %s\n" $i $arg
  i=`expr $i + 1`
  str="$str $arg + "
done

sum=`echo $str 0 | bc`
echo "The sum is $sum"

```
bc: An arbitrary precision calculator language

## dc
```shell=
#!/bin/bash

echo "Number of argument is : $#"

i=0; op=""
for  arg in $*; do
  printf "arg[%2d] = %s\n" $i $arg
  i=`expr $i + 1`
  op="$op +"
done

sum=`echo "0 $* $op p" | dc`
echo "The sum is $sum"

```
dc: an arbitrary precision calculator


## While
```shell=
#!/bin/bash

# this program reads from stdin, one number per line

i=1; sum=0
read arg
while [ $arg != "q" ];  do
  printf "arg[%2d] = %s\n" $i $arg
  i=`expr $i + 1`
  sum=`expr $sum + $arg`
  read arg
done

echo "The sum is $sum"
```

不斷輸入，直到 q 


## Function
```shell=
#!/bin/bash

sum=0

sigma()
{
  if [ $1 -le 0 ]; then  return;  fi

  sum=`expr $sum + $1`
  sigma `expr $1 - 1`
}


sigma ${1-0}
echo $sum
```

## Hanoi_Tower
```shell=
moveDisk()
{
    echo from "$1" to "$2"
}
moveTower()
{
    if [ "$1" -eq 1 ]; then
        moveDisk $2 $4
    else
        moveTower `expr $1 - 1` $2 $4 $3
        moveDisk $2 $4
        moveTower `expr $1 - 1` $3 $2 $4
    fi
}

num=$1
moveTower $num 'A' 'B' 'C'
```

```
$ ./Hanoi_Tower.sh 3
from A to C
from A to B
from C to B
from A to C
from B to A
from B to C
from A to C
```