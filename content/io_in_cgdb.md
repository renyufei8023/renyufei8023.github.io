Date: 2013-10-07
Title: 在cgdb中进行I/O交互
Category: Tech
Tags: cgdb
Slug: io_in_cgdb

cgdb，gdb -tui的加强版，非常优秀，中文教程在此：<https://github.com/leeyiw/cgdb-manual-in-chinese/blob/master/contents.md>，不再赘述。

cgdb有一个问题困扰了我很久：如何方便地进行I/O交互。

虽然cgdb自带了TTY模式，但不太靠谱，调试到某些Unix I/O接口时会卡死，如read函数。

今天我又反复看了下教程，发现了这样一句以前没注意的忠告：
> 如果被调试的程序需要读取终端用户输入，我们推荐用户在终端中启动被调试程序，然后在另一个终端使用CGDB去attach被调试程序，这是与被调试程序进行I/O交互最简单的方法。

但是教程没有说具体该怎么操作，摸索了下，终于完美解决，以调试redis-cli为例。

1. 命令行先后启动redis-server和redis-cli；
2. ps查到redis-cli进程号后直接cgdb -p [pid]；
![1](https://lh6.googleusercontent.com/-5Eq0HZugi_0/UlGfDvp545I/AAAAAAAAASE/EUUwYqy23aY/w788-h124-no/Screen+Shot+2013-10-07+at+1.33.30+AM.png)
3. 进入cgdb后不要慌，用bt看下阻塞I/O在哪里；
![2](https://lh4.googleusercontent.com/-g3Mq_Eg2aGI/UlGf0iupLjI/AAAAAAAAASY/rApjcwZpibw/w958-h112-no/Screen+Shot+2013-10-07+at+1.36.55+AM.png)
4. 然后在阻塞I/O处设置断点，可以看到这里在linenoise.c的312行调用了read()，直接加断点b linenoise.c:312；
5. cgdb中输入continue，然后再去redis-cli那里输入想调试的命令，比如info，回到cgdb，发现源码已经刷出来了，大功告成。
![3](https://lh4.googleusercontent.com/-2k_4-6EXv1I/UlGhLX__87I/AAAAAAAAATA/2PIFr0YZv8c/w958-h599-no/Screen+Shot+2013-10-07+at+1.42.54+AM.png)






