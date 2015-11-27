Date: 2014-05-25
Title: Git历险记
Category: Tech
Tags: git
Slug: a_git_adventure

Git, beautiful software.

很多SVN使用者刚刚转到Git时，都会为Git独特的使用方式感到疑惑，尤其是Git大名鼎鼎的分布式思想、随时随地的本机开发、独一无二的暂存区、难以置信的轻量级分支、无处不在的fork。

这些都让Git显得如此与众不同，

当很多人从一个软件迁移到另一个软件并不再回头的时候，就值得我们注意了。

这说明另一个软件**更好用**。

当我们说某个软件更好用的时候，这意味着以下几个问题：为什么很多人都说它好用？具体好用在哪里？它的内部究竟是怎样设计的？为什么要这样设计？

带着这些疑惑，让我们走进Git内部的神秘世界。

##Git对象
* * *
每一位git使用者，都会不由自主地思考这样一件事情：git究竟是怎么存储每个文件和提交历史的？

###Blob对象

我们在本地新建一个git仓库

    git init learn-git

会发生该目录下多了一个.git文件夹，进去后长这样：
    
    .git/
    |-- HEAD
    |-- config
    |-- description
    |-- hooks
    |   |-- applypatch-msg.sample
    |   |-- commit-msg.sample
    |   |-- post-commit.sample
    |   |-- post-receive.sample
    |   |-- post-update.sample
    |   |-- pre-applypatch.sample
    |   |-- pre-commit.sample
    |   |-- pre-rebase.sample
    |   |-- prepare-commit-msg.sample
    |   |-- update.sample
    |-- info
    |   |-- exclude
    |-- objects
    |   |-- info
    |   |-- pack
    |-- refs

* description文件仅供GitWeb使用，不用关心它。
* config文件包含了项目特有的配置选项，如最常用的用户名和邮箱。
* info目录保存了一份不希望在 .gitignore 文件中管理的忽略模式 (ignored patterns) 的全局可执行文件。这个用得比较少，也不用太关心。
* hooks目录保存了客户端或服务端钩子脚本，一般我们都是用默认的，很少改，也不用太关心。

因此，我们需要重点关心另外四个重要的文件或目录：HEAD和index文件，objects和refs目录，因为它们是Git的核心：

* objects 目录存储所有数据内容。
* refs 目录存储指向数据 (分支) 的提交对象的指针。
* HEAD 文件指向当前分支。
* index 文件保存了暂存区域信息。

接下来，我们新建一个文件1.txt，内容为1，并把它加入暂存区
    
    ➜ echo 1 > 1.txt
    ➜ git add 1.txt

于是我们发现.git目录下多了2个文件，且内容都为字节码：
    
    .git/
    |-- index
    |-- objects
    |   |-- d0
    |   |   |-- 0491fd7e5bb6fa28c517a0bb32b8b506539d4d

使用如下命令查看1.txt的hash值
    
    ➜ git hash-object 1.txt
    d00491fd7e5bb6fa28c517a0bb32b8b506539d4d

我们发现结果的前2位是文件夹的名字，后38位是文件的名字。

其实0491fd7e5bb6fa28c517a0bb32b8b506539d4d这个文件是用zlib压缩的，我们用Python解压一下：
    
    >>> import zlib
    >>> zlib.decompress(open(".git/objects/d0/0491fd7e5bb6fa28c517a0bb32b8b506539d4d").read())
    'blob 2\x001\n'
    
 反向验证一下：
     
    >>> import hashlib
    >>> hashlib.sha1('blob 2\x001\n').hexdigest()
    'd00491fd7e5bb6fa28c517a0bb32b8b506539d4d'
    
即git使用'blob ' + len(content) + '\0' + content作为文件内容，其sha1值的前2位作为文件夹名，后38位作为文件名。 

这就是git blob对象的奥秘。

下面瞅瞅index文件，查看index文件的内容可以用这个命令：
    
    ➜ git ls-files --stage
    100644 d00491fd7e5bb6fa28c517a0bb32b8b506539d4d 0 1.txt

依次为文件的访问权限、文件sha1值、版本号、文件名。

index文件并不像blob文件那样简单的用zlib压缩，而是基于一个稍许复杂的协议，在github上可以找到：<https://github.com/git/git/blob/master/Documentation/technical/index-format.txt>。

github上也有一个用来解析index的Python3程序gin：<https://github.com/sbp/gin>，核心思路在于按协议依次读入字节时先把网络序转化为主机序，再按格式把字节流转化成字符串。

解析的结果如下：
    
    [header]
      signature = DIRC
      version = 2
      entries = 1

    [entry]
      entry = 1
      ctime = 1401014438.0
      mtime = 1401014438.0
      dev = 16777218
      ino = 134288315
      mode = 100644
      uid = 501
      gid = 20
      size = 2
      sha1 = d00491fd7e5bb6fa28c517a0bb32b8b506539d4d
      flags = 5
      assume-valid = False
      extended = False
      stage = (False, False)
      name = 1.txt

    [extension]
      extension = 1
      signature = TREE
      size = 25
      data = "\u00001 0\n8\u00fd)i{\"\u000f~L\u00a1[\u0004L2\"\u00ee\u00feZ\u00fd\u00c1"

    [checksum]
      checksum = True
      sha1 = ffebb80862254fef8c72af2acfa6ac035d98f5dd

###Tree对象和Commit对象

现在我们提交一次：
    
    git commit -m 'first ci'
    
objects目录下多了两个文件，查看一下内容：
    
    ➜ git cat-file -p 38fd29697b220f7e4ca15b044c3222eefe5afdc1
    100644 blob d00491fd7e5bb6fa28c517a0bb32b8b506539d4d 1.txt
    ➜ git cat-file -p 844d93360ba0083ae4a6e911887a569892cb5102
    tree 38fd29697b220f7e4ca15b044c3222eefe5afdc1
    author lizherui <lzrak47m4a1@gmail.com> 1401017562 +0800
    committer lizherui <lzrak47m4a1@gmail.com> 1401017562 +0800
    
    first ci

即生成了一个tree对象和一个commit对象：commit对象指向这个tree对象，这个tree对象指向1.txt文件。

这个tree对象可以认为是.git文件夹所在的目录，即根目录，类似unix文件系统中的"/"。

我们新建一个文件dir，在里面建一个新文件2.txt，并提交：

    mkdir dir
    cd dir && echo 2 > 2.txt
    git commit -am 'second ci'

查看一下第二次提交：
    
    ➜ git cat-file -p b2b2ec533fbfe31801fc5571e812ac6a3bd9e46d
    tree 80ab0595bc80fab8778b3c5011c49bf7ea475241
    parent 844d93360ba0083ae4a6e911887a569892cb5102
    author lizherui <lzrak47m4a1@gmail.com> 1401018309 +0800
    committer lizherui <lzrak47m4a1@gmail.com> 1401018309 +0800

    second ci
    
整个看起来像是这样：

![1](https://lh6.googleusercontent.com/-hgr8Hbh5KQM/U4HapRamrKI/AAAAAAAAAgk/pUxyLw9wwAM/w769-h367-no/Screen+Shot+2014-05-25+at+19.54.42.png)

这就是git的对象系统，本质上是一个key-value的内容寻址文件系统。

我们发现git为每个文件都存储了快照，而不是像svn那样记录增量修改。如果一个大文件只改了1行，git仍然会为其新建一个快照。这就带来了一个问题：git的这种设计思想会占用很大的存储空间，显得很浪费。

在这一点上，git真的无能为力吗？

##Git压缩
* * *

我们新建一个100w行都为3的文件3.txt并提交，然后把第一行改成4再提交。

我们发现有2个12k的快照：
    
    ➜ du -sh ./* |grep 12K
    12K	./9b
    12K	./ce

磁盘上有了两个几乎完全相同的12K的对象。如果Git只完整保存其中一个，并保存另一个对象的差异内容，岂不更好？

事实上 Git 可以那样做。Git 往磁盘保存对象时默认使用的格式叫松散对象 (loose object) 格式。Git 时不时地将这些对象打包至一个叫 packfile 的二进制文件以节省空间并提高效率。当仓库中有太多的松散对象，或是手工调用 git gc 命令，或推送至远程服务器时，Git 都会这样做。手工调用 git gc 命令让 Git 将库中对象打包并看会发生些什么：
    
    ➜ git gc
    Counting objects: 20, done.
    Delta compression using up to 4 threads.
    Compressing objects: 100% (15/15), done.
    Writing objects: 100% (20/20), done.
    Total 20 (delta 6), reused 0 (delta 0)

查看一下object目录，原来的object都没了，在pack文件夹下生成了2新文件：
    
    ➜ find .git/objects -type f
    .git/objects/info/packs
    .git/objects/pack/pack-ee129ceb0468a3cf3ba3aa6023a317df104c2f44.idx
    .git/objects/pack/pack-ee129ceb0468a3cf3ba3aa6023a317df104c2f44.pack

查看idx文件：
    
    ➜ git verify-pack -v .git/objects/pack/pack-ee129ceb0468a3cf3ba3aa6023a317df104c2f44.idx
    9b84452867f54e90019ae876477060784a08ac50 blob   2000000 1968 1107
    ce01eef250562995d118fdae4d5f9836d89fe483 blob   102 87 3231 1 9b84452867f54e90019ae876477060784a08ac50

果然是增量保存，ce01e只有102字节。

Git自动定期对仓库进行重新打包以节省空间，当然也可以手工运行 git gc 命令。

##Git分支 
* * *

SVN中新建分支是个昂贵的过程，常常需要创建一个源代码目录的完整副本，对大型项目来说会花费很长时间。

>Git的分支可谓是难以置信的轻量级，它的新建操作几乎可以在瞬间完成，并且在不同分支间切换起来也差不多一样快。和许多其他版本控制系统不同，Git鼓励在工作流程中频繁使用分支与合并，哪怕一天之内进行许多次都没有关系。理解分支的概念并熟练运用后，你才会意识到为什么Gi 是一个如此强大而独特的工具，并从此真正改变你的开发方式。
 
我们创建一个分支test_branch，并切换过去:
    
    git branch test_branch
    git checkout test_branch
    
我们发现HEAD文件的内容指向了新文件refs/heads/test_branch
    
    ➜ cat .git/HEAD
    ref: refs/heads/test_branch
    
    ➜ cat .git/refs/heads/test_branch
    ab779b378043dbb4fa4436cab8263f4a5ba8d26a
        
修改一下1.txt并提交，test_branch指向了新的commit
    
    cat .git/refs/heads/test_branch
    7622a8a51a02d7843026589c71e587b7ad123c1c

切回master，一切未变，master仍然指向老的commit：ab779b3

这时候我们在master里把test_branch合进来：

    ➜ git merge test_branch
    Updating ab779b3..7622a8a
    Fast-forward
     1.txt | 2 +-
     1 file changed, 1 insertion(+), 1 deletion(-)
发生了什么？master的commit从ab779b3变成了test_branch的commit对象7622a8a。

于是我们看到，分支在git中就是一个指向某个commit对象的指针，记录在refs文件夹中，增加分支/删除分支/合并分支全部是在操作指针。

How beautiful it is!

##Git远程传输
当我们输入git clone xxx的时候，究竟发生了什么？

其实很简单，在Https的基础上git会去获取远程仓库的当前commit对象，然后一个一个http get到本地。

偷个懒，详细过程请看：<http://git-scm.com/book/en/Git-Internals-Transfer-Protocols>

##总结
2005年，Linus Torvalds受够了市面上的版本控制软件，为了更好的管理Linux Kernel项目而开发了Git，最初的设计思想是：
    
* 分布式工作流
* 防止内容受损的安全措施
* 高性能

今天，当我们打开[Git官网](http://git-scm.com)，**--everything-is-local**仍然被摆在最醒目的位置上。git独特的设计决定了它完全支持离线工作、离线提交、离线访问历史记录的功能。

Why?

Local means fast and stable.

人人都喜欢在本地工作，快速、稳定、不依赖网络传输。

此外，本地开发意味着“去中心化”的分布式思想，每个人的机器上都是一个Git仓库，互相可以任意push和pull，而且这也相当于用类似“冗余”的手段实现了高可用性，中央仓库挂了也没事。

所以仔细品味一下，支持本地离线开发是多么传奇而伟大的设计。

此外，Git基于完整文件快照而非增量变更的设计，使分支成为了**真正的**分支，简洁、快速而强大，一切分支操作都显得那么得自然、流畅。

当我们说一个软件很棒的时候，不仅仅是说它好用，更是在说它内部优美的设计。我们会不由自主地ask why，并在好奇心的驱使下进入内部一探究竟。

探寻像Git这样富有传奇性的软件内部无疑是一件趣味性极强的事情，甚至能感受到一种软件设计的哲学思想。

这种哲学给人的感觉就是，Git就像是在未来世界设计的软件，然后穿梭回来给世人使用。

Too fast, too clean, too strong, and too good.

Why?

Linus Torvalds认为svn极度依赖中央仓库缺乏高可用性，于是设计了分布式工作流；觉得svn分支过于重量级显得很愚蠢，于是设计了完整快照+分支指针的模型；觉得svn大量操作依赖网络io显得很慢，于是设计了本地离线开发模式。

这让我想起来一篇伟大的文章：[How to Get Startup Ideas](http://paulgraham.com/startupideas.html).

生活中我们常常问“怎样才能**想出来**一个优美设计”的时候，究竟在问什么？

优美的设计真的是**想出来**的吗？

> Noticing , not coming up with.
  
> Live in the future, then build what's missing. 

于是Git横空出世，犹如后来的iphone。

多么酷，多么美，多么令人着迷。

所以问题的关键来了，怎样才能具备**观察**缺失的能力，首先我们需要成为擅长观察缺失的人，这意味着批判式思维，各个软件的设计不再让我们感到理所当然，就像2005年人们都觉得svn已经够好了，Linus Torvalds却仍然觉得很不爽。

开始观察软件/生活中让我们感到不爽的地方并思考怎样去改进是一件很累的事情，但这种累并不意味着我们自身出了问题。

也许，只是我们跑得太快了。















