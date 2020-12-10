###### tags: `UNIX`

# awk

```shell=
if(s ~/^[a-zA-Z]/)
```
如果開頭為a ~z 或 A~Z

```shell=
if(s ~/^[0-9]/)
```
如果開頭為0-9

```shell=
for(i=1;i<=NF;i++){
    print i
}
```
NF為那行的最後一項，所以是輸出每行的每欄的資料
