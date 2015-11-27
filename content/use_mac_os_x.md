Date: 2013-08-11
Title: 为什么我一直强烈推荐程序员使用Mac OS X
Category: Tech
Tags: mac os x, macintoch
Slug: use_mac_os_x

像绝大多数国内程序员一样，我在相当长的时间里对Mac OS X一无所知，最开始使用Windows进行开发，然后转到Linux。

去年11月我终于攒够钱了，决定试着从Linux转到Mac OS X，于是入手Macbook Pro，从此踏上了Mac OS X的道路，没想到一去不复返。

这一年来使用Mac OS X的经历，不仅极大地开拓了我的视野，而且在很大程度上改变了我对待软件开发的态度。当然了，最重要的是，它使我的开发效率有了质的提升。

##Macintosh在国内的现状
Macintosh，即搭载着Mac OS X操作系统的苹果电脑，在国内的市场份额一直少得可怜，甚至在程序员这样的团体中亦是如此。

是因为Macintosh太贵了？还是因为Mac OS X不兼容Windows的一些软件？虽然这两条理由确实会打消广大普通用户购买Macintosh的念头，但是对于国内程序员来讲，这俩显然都不是问题。

那到底是什么原因阻碍了绝大多数国内程序员使用Mac OS X呢？

我仔细观察过这个事情很长时间，后来越来越明晰地发现，最根本的原因是绝大多数国内程序员完全都不知道Mac OS X是什么，更别提使用Mac OS X能给自己带来哪些好处了。

##Mac OS X首先是Unix
没错，Mac OS X是Unix，这是最重要的一点，而很多很多国内程序员都不知道。

这是Wikipedia对Mac OS X的部分描述：Mac OS X于1998年首次推出，并从2002年起随Macintosh发售。它是一套Unix基础的操作系统，包含两个主要的部份：核心名为Darwin，是以FreeBSD源代码和Mach微核心为基础，由苹果公司和独立开发者社区协力开发，以及一个由苹果计算机开发，名为Aqua之专有版权的图形界面。

在命令行执行uname -a可以看到:
![1](https://lh6.googleusercontent.com/v4Y0Fq4yLwoyn9aNLPllnXuooi_0pxbf4v3QUhyDQGk=w958-h40-no)

Mac OS X甚至比Linux具有更纯正的Unix血统，它是真正的Unix，符合标准，有授权，可以合法地用Unix商标。

##Unix环境意味着什么
对于非c#/.net系程序员来讲，一套Unix环境绝对是必备的，尤其是C、C++、PHP、Python、Ruby程序员。Java程序员倒不是那么依赖Unix环境，但使用Unix环境只会如虎添翼。

我回想起使用Windows开发C/C++/Python的那段日子，最痛苦的事情倒不是有些软件只支持Unix环境，而是当开发过程中遇到一些Windows环境下特有的奇奇怪怪的问题时，Google都搜索不到相应的解决方案，因为活跃的开发者大多使用Unix环境。

这样的事情发生多了，就会让开发人员感到越来越沮丧，进而绝望。

于是像大多数程序员一样，我开始学习使用Linux。

##Linux操作系统的问题
就开发程序而言，Linux没有什么问题。

Linux最大的问题之一在于桌面软件实在太少，连基本的搜狗输入法、QQ都没有，更别提其它的了。

这就导致我们必须要经常在Linux和Windows之间切换：在Linux下开发，在Windows下做开发以外的事情。

这样的事情做久了，就会越来越厌烦。

Linux还有一个大问题就是图形界面太渣，而且很不稳定，实在是无力继续吐槽。

于是，一个自然而然的需求便会越来越强烈：有没有既含Windows这样靠谱的图形系统以及广大的常用软件，又有高效的Unix命令行环境的一站式解决方案呢？

答案就是Mac OS X。

##Mac OS X的其它优势
除了上述所说的Mac OS X既含有程序员必备的Unix命令行环境，又具备高端大气上档次的图形界面这一招牌优势外，Mac OS X中还有很多强悍的利器。

###眼花缭乱的手势
我们看到使用macbook的人很少使用鼠标，不是因为他们忘了带，而是根本不需要鼠标，因为触摸板+手势完爆鼠标。

Macbook的触摸板无疑是世界上最出色的：轻拍点按，双指右键，双指上下滚动，三指查找，三指拖移，四指左右切换全屏程序，四指上推显示Mission Control，四指下推显示Expose，四指合拢显示Launchpad，四指张开显示桌面。。。。。。

而且由于触摸板离键盘很近，我们能很方便地以手掌为轴心在触摸板和键盘之间旋转切换，而不需要像使用鼠标+键盘那样很麻烦地把整只手移来移去。这一点很重要，无时无刻都在极大地提高开发效率。

###设计优美的软件
Mac OS X上的软件外貌优美，风格统一，没有乱七八糟的广告和病毒，也不需要360这样强奸用户的软件。一切都是绿色的、纯天然的。

###独一无二的字体渲染
Mac OS X的字体渲染效果是最好的，完爆Windows/Linux。在Windows上有一个模仿Mac OS X字体渲染效果的软件叫Mactype，但仍然不能与Mac OS X的字体渲染效果相提并论。大名鼎鼎的Monaco字体有着程序员专用字体的美称，同样来自Mac OS X。

这是命令行下的字体效果：
![2](https://lh5.googleusercontent.com/-K5cnpKlXKwc/UgfGws5tvzI/AAAAAAAAAJ4/cXOTHfdjWRQ/w728-h350-no/%25E5%25B1%258F%25E5%25B9%2595%25E5%25BF%25AB%25E7%2585%25A7+2013-08-12+%25E4%25B8%258A%25E5%258D%25881.15.00.png)

这是Vim中的字体效果:
![3](https://lh5.googleusercontent.com/-CrhmcI9FC4Q/UgfG-YrNY1I/AAAAAAAAAKA/1ytp9t3SWto/w724-h612-no/%25E5%25B1%258F%25E5%25B9%2595%25E5%25BF%25AB%25E7%2585%25A7+2013-08-12+%25E4%25B8%258A%25E5%258D%25881.16.22.png)

###行云流水的快捷键
Mac OS X上的快捷键随处可见，能随心所欲地定制，并且大多以Command为组合快捷键中的主键，用大拇指按起来极其顺手，让人渐渐忘却了Windows/Linux上用小拇指费劲地按ctrl/alt的痛苦日子。

###强悍易用的软件包管理器
Homebrew，Mac OS X上强悍的软件包管理器，使用Ruby开发，托管在github上：<https://github.com/mxcl/homebrew>。我用过Ubuntu上的apt，也用过Fedora上的yum，但它俩实在无法跟Homebrew相提并论。
##结束语
无它，唯Mac OS X。















