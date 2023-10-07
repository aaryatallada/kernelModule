# A Kernel Seedling
Building a /proc/count file to show the number of current process running. The process table runs within kernel mode, so in order to access it I wrote this kernel module that also runs in kernel mode. I use a struct to iterate through the processes running and for each process, I increment a counter n initialized to 0 by 1 effectively counting each process. 

## Building
```shell
make clean (optional to remove excess from last build)
make
```

## Running
```shell
sudo rmmod proc_count.ko (optional to remove kernel module if you have uploaded previously)
sudo insmod proc_count.ko
cat /proc/count
```
TODO: results?

## Cleaning Up
```shell
make clean
sudo rmmod proc_count.ko
```

## Testing
```python
python -m unittest
```
Results:
Ran 3 tests in 8.190 s
OK


Report which kernel release version you tested your module on
(hint: use `uname`, check for options with `man uname`).
It should match release numbers as seen on https://www.kernel.org/.

```shell
uname -r -s -v
```
Kernel Version: 
5.14.8-arch1-1
