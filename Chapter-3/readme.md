# 文件 I/O


## 3.3 open openat

```c
#include <fcntl.h>
int open(const char *path, int oflag,... /* mode_t mode */);
int openat(int fd, const char *path, int oflag, ... /* mode_t mode */ );
                                                两函数的返回值：若成功，返回文件描述符；若出错，返回−1
```

###

由open和openat函数返回的文件描述符一定是最小的未用描述符数值。

## 3.4 create

```c
#include <fcntl.h>
int creat(const char *path, mode_t mode);
                                          返回值：若成功，返回为只写打开的文件描述符；若出错，返回−1
```

create一个不足之处是它以只写方式打开所创建的文件。（无法读文件）

## 3.5 close

```c
#include <unistd.h>
int close (int fd);
                    返回值：若成功，返回0；若出错，返回−1
```

关闭一个文件时还会释放该进程加在该文件上的所有记录锁。

当一个进程终止时，内核自动关闭它所有的打开文件。

## 3.6 lseek

可以调用lseek显式地为一个打开文件设置偏移量。

```c
#include <unistd.h>
off_t lseek(int fd, off_t offset, int whence);
                                              返回值：若成功，返回新的文件偏移量；若出错，返回为−1
```

## 3.7 read

```c
#include <unistd.h>
ssize_t read(int fd, void *buf, size_t nbytes);
                                            返回值：读到的字节数，若已到文件尾，返回0；若出错，返回−1
```

    ssize_t -> 带符号整型
    size_t -> 不带符号整型

## 3.8 write

```c
#include <unistd.h>
ssize_t write(int fd, const void *buf, size_t nbytes);
                                                       返回值：若成功，返回已写的字节数；若出错，返回−1
```

## 3.9 I/O 的效率



## 3.10 文件共享




