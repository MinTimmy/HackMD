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
;;：一個