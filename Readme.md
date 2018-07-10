
Record data:

```
perf record -F 99 -a -g -- sleep 10
perf script > out.perf
```

Get folded data && sort:

```
./stackcollapse-perf.pl out.perf > out.folded
awk '{print $NF,$0}' out.folded | sort -nr | cut -f2- -d' ' | less
```
