Date: 2014-03-23
Title: 阅读英文原版的初步体验
Category: Life
Tags: English book
Slug: beginning_of_reading_English_books

2月下旬年假结束回杭，开始执行“英文原版阅读计划”，到今天差不多一个月了。我使用[Dropbox](https://www.dropbox.com/sh/hgihoqsrpnjnl2d/h4bEwUWgZl/en)分享所有的英文书籍。

这一个月的战况依次是：

* [《Hackers And Painters》](https://www.dropbox.com/sh/hgihoqsrpnjnl2d/89Q--qQyUi/en/tech/Hackers%20And%20Painters.pdf)

* [《The Google Resume》](https://www.dropbox.com/sh/hgihoqsrpnjnl2d/4VBvBXi1bg/en/life/The%20Google%20Resume.pdf)

* [《The Cathedral And The Bazaar》](https://www.dropbox.com/sh/hgihoqsrpnjnl2d/W45SVrZhtx/en/tech/The%20Cathedral%20And%20The%20Bazaar.pdf)

* [《The Google File System》](https://www.dropbox.com/sh/hgihoqsrpnjnl2d/f8u1epma2V/en/tech/The%20Google%20File%20System.pdf)

* [《Bigtable-A Distributed Storage System for Structured Data》](https://www.dropbox.com/sh/hgihoqsrpnjnl2d/iFsPI7IqnL/en/tech/Bigtable-A%20Distributed%20Storage%20System%20for%20Structured%20Data.pdf)

* [《MapReduce-Simplied Data Processing On Large Clusters》](https://www.dropbox.com/sh/hgihoqsrpnjnl2d/8eT0j1J63f/en/tech/MapReduce-Simplied%20Data%20Processing%20on%20Large%20Clusters.pdf)
 
在这之前，只阅读中文技术资料的习惯使我总会不由自主地排斥英文资料，一碰到英文的技术资料，脑子里的第一反应就是：擦，英文的！赶紧去搜一下有木有翻译版。此外，浏览[Quora](http://www.quora.com/)、[StackOverflow](http://stackoverflow.com)这样的英文网站时，阅读任何英文问答都很没有耐心。

我相信很多人都是这样的。

就像上一篇博文所说的，我还想再重复一次：这种状态让我意识到了一个非常严重的问题，排斥英文资料相当于给自己**设限**，会让自己错过更优秀的知识和资料(众所周知，最好的技术资料往往都是英文的)。这会阻碍我们的成长，所以这个问题必须得到解决。

这一个月下来，从半技术的英文书籍入手，过渡到谈论架构的英文论文，目前我感觉非常非常好，下一步准备阅读以技术细节为主的英文书籍，如[《Inside The Java 2 Virtual Machine》](https://www.dropbox.com/sh/hgihoqsrpnjnl2d/I0a4-AnN_N/en/tech/Inside%20The%20Java%202%20Virtual%20Machine.pdf)。

在实践中，我发现了一个现象，让我感到尤为惊讶：有很多细节，是**“不可翻译的”**。一个段落或一篇文章中**“不可翻译”**的部分越多，翻译版与英文原版的差别就会越大。这一点在阅读Google的那3篇著名论文中表现得尤为明显，我曾尝试过阅读翻译版好几次，但每次读到一半就会产生不知所云的感觉，最终半途而废。没想到这次试着读了下英文原版，居然一次成功，完完整整地读了下来，并且基本弄明白了意思。

Why?

Google这三篇论文太长，我举一个短点儿的例子。

[《The Philosophy of Open Source》](https://www.dropbox.com/sh/hgihoqsrpnjnl2d/FNKQ4YUlbv/en/tech/The%20Philosophy%20of%20Open%20Source.pdf)这本书，以著名的“Linux kernel management style by Linus Torvalds”结尾，这一段由啄木鸟社区(啄木鸟社区的水平还是相当高的)翻译如下：

```
1.1 导言
Linus Torvalds 在2004年把一篇讲"Linux内核的管理风格"的文章放在了内核源码文档里。这篇文章有意对应他以前写的关于编码 风格的文章（比如烧书仪式），也有技术人员熟悉的Dilbert卡通的影子。 Henrik Ingo 写"Open Life: The Philosophy of Open Source"一书的时候，拿这篇文章作了后记。

这篇文章其实是总结了Linus十几年里领导开源运动的经验。更重要的是，它讲述了一种与传统不同的做事理念，一种后互联网时代的、尊重技术和自由的理念。

Linus的写作诙谐生动，完全不同于ESR的《大教堂和市集》。所以我作了比较自由的翻译。以下是译文。

1.2. Linux内核的管理风格
（Linux kernel management style, by Linus Torvalds. Retrieved from http://openlife.cc/node/43, Jan-28-2008）

这个简单文档描述Linux内核偏爱的（或编造的，取决于你问谁）管理模式。它在一定程度上是编码风格文档的影子，主要写来避免一遍又一遍回答同一类问题＊。

管理风格是很个人化的，比起简单的编码风格条例更难量化，所以这个文档跟现实可能沾边也可能不沾边。它开始于游戏，但是不见得就不作数。你只有自个儿决定。
顺便说一下，我们说到"内核管理者"的时候，完全是说技术带头人，不是公司里那些作传统管理工作的人。如果你是在订单上签名的人或者对你们组的预算知道一丁半点，你几乎一定不是个"内核管理者"。这些建议对你可能适用也可能不适用。
首先，我建议你买一本《高度成功人士的七个习惯》，不－要读它，烧了。表一下决心。
（＊） 这个文档不见得"回答"多少问题，更大程度上是展示我们的无知，让提问者死了这条心。
不管怎样，开讲了：

1.2.1. 第一章：决定
每个人都觉得管理者是作决定的，作决定是很重要的。决定越大、越艰难，管理者就越伟大。这一点很深刻、很明显，但不见得正确。

事情的要义是避免－作决定的必要性。特别是，当有人告诉你"是甲还是乙，我们需要你来作决定"，你作管理的麻烦就来了。你手下的人一般比你更懂具体问题，所以要是他们找你作一个技术性的决定，你死定了。要替他们作决定，你显然水平不够。
（推论：如果你手下的人不比你更懂具体问题，你还是死定了，尽管出于完全不同的原因。说白了就是你站错了岗位，应该他们－来管理你的才华才对。）

所以要义是避免－决定，至少避免大的和艰难的决定。作小的、不重要的决定还好了，而且让你挺挺板板、面上有光。所以一个内核管理者需要的是把大的艰难的决定变成没人在乎的小事情。
帮你点拨一下，大决定和小决定的区别在于你能否事后修补得了。如果你犯错了的时候（而且你会－犯错），你能返回来弥补损失，那么你可以把任何的决定变成"小决定"。一下子，你的表现机会多了一倍：你要作两－个不重要的决定，错误决定"加上"正确决定。
而且大家甚至会认为这是领导才能（咳咳，狗屁，咳咳）。因此避免作重大决定的要点成了仅仅避免做不可逆反的事情。不要被牵引到一个无路可逃的角落里。困在角落里的耗子或许是危险的，困在角落里的管理者不过是个可怜虫。
事实上，不管怎样－，没有人会愚蠢到让一个内核管理者承担太大的财政责任，所以纠正错误一般不是多难。既然你没有机会浪费掉你倾家荡产也还不清的巨额经费，你要纠正的不过是一个技术性的决定。那就好办了：告诉每个人你是个不称职的白痴，说对不起，把你让大家上一年作的无用功都扔掉。一下子，你一年前作的决定也不见得是什么重大决定，既然能简单的撤销掉。
然而事实上，有些人搞不来这个办法。有两个原因：
（一）承认自己是傻瓜做起来蛮难的。我们都喜欢保持形象，公开认错有时候是很困难。
（二）对下级的工程师来说，被人告知自己上一年的工作落得一文不值，也是很恼火的。实际的工作结果－可以删除了事，但你可能就永久性的失去了这个工程师的信任。记住，"永久性"是我们要避免的第一件事，这样你的决定最终还是一个重大决定。
所幸的是，你对两个原因都可以棋高一着，未雨绸缪，防患未然。办法是：事先就承认你狗屁不懂，告诉大家你的决定不过是摸着石头过河，说不定就掉河里了。
你应该永远保留改变决定的权利，而且要让大家明白－这一点。而且在你做了真正的傻事之前承认你是个傻瓜要容易的多。
这样，当事情真的到了傻冒的地步，人们不过是翻下眼皮，说："唉......真是灵验啊......"
这种事先承认不足的做法可能还会让下面真正做事的人三思而后行，想一下值不值。说回来，如果他们－都不确定是个好主意，你铁定了不应该给他们开绿灯，煽风点火。至少要让他们在开始大动作之前好好想一下。
记住：他们在细节上应该知道的比你多，而且他们一般觉得一切已在掌握之中。作为管理者，你能做的最好的事情不是给他们填充信心，而是给他们适量的批判理性。
顺便说一下，另外一个避免决定的办法是装可怜，简单地问"我们为什么不能两个都做呢？" 相信我，这个有用。如果不清楚哪条路子更好一些，他们最终会整明白的。答案或许是两帮人都挫败灰心，双双放弃。
这听起来像是个失败，但它一般是两个项目都有问题的迹象，大家无法决定的原因是双方都错了。结果是你成了智慧的舵手，而且你又避免了一个本来会死得很难看的决定。

1.2.2. 第二章：人
大多数人都是傻瓜，当管理者就意味着你不得不和这一点打交道。或许更重要的是，他们－不得不和你－打交道。

事实证明，消除技术性问题还是容易的，消除人脑筋里的问题就没那么容易了。你就不得不忍受这些问题，他们的还有你自个儿的问题。
然而，为了做好内核管理者，最好记住不要自绝后路，伤及无辜，或树敌过众。现实是，疏远人们是蛮容易的，把他们拉拢回来就难了。因此"疏远"直接归类到"不可逆反"的事情里，就是第一章里说的大忌。

这里只有两条简单的规则：
（一）不要骂人猪头（至少不要在公开场合下）
（二）要是你忘了第一条，学会怎样道歉
第一条的问题是太容易违反，因为你有一万种骂人猪头的办法＊，有时不自觉就骂了，而且几乎总是义愤填膺、义正严词。
而且你越是骂的热血沸腾（让我们来面对事实，你可以骂几乎任何－人猪头，你往往不－会骂错），事后你越难道歉。
要解决这个问题，你其实只有两条路子：
（一）成为道歉专家
（二）"遍洒博爱，处处留情"，这样没有人会觉得受到了特殊待遇。骂出新意，骂出水准，他们没准会找到艺术的享受。
第三条路子，始终如一的作谦谦君子，是行不通的。没有人会信任城府太深的人。
＊保罗西蒙的歌唱道"失恋五十种"，是因为老实说，"骂一个程序员猪头一万种"没有那么押韵。不过我相信他肯定考虑过这个。

1.2.3. 第三章：能人
尽管现实是大多数人都是傻瓜，不幸的推论包括你也是傻瓜之一，尽管我们都心安理得的自认比傻瓜高明（让我们来面对事实，没有人自认傻瓜或不如傻瓜），我们还是应该承认我们不是独步江湖，总会有一些人不像我们一样的傻瓜。一些人嫉贤妒能，另一些人从善如流。

确定你，作为一个内核管理者，属于第二种。贴紧了高手能人，因为他们会使你的工作变容易。特别是，他们将能够替你作决定，这正是事情的要义。
所以你要是发现了比你聪明的人，顺水推舟好了。你的管理职责很大程度上就成了说一下"听起来是个好主意，放手去干吧"，或者"这个不错，那个XXX怎么样呢？"。第二个版本尤其有效：你要么学到一些关于"XXX"的新东西，要么指出了聪明人都没想到的东西，表现得胸有－韬略。随便那种情况，你都是赢家。
另外一件要小心的事情是，一个人在一方面厉害不见得在其他方面也厉害。你或许煽动谁做什么，但是让我们来面对事实，他或许精通自己的一亩三分地却其他什么都做不来。好的消息是，人们自然而然的倾向于选择自己擅长的事情来做。所以你真的－煽动一下，一般不见得会造成什么不可逆反的后果，只是不要用铁扇公主的芭蕉扇来煽。

1.2.4. 第四章：担当
事情总会出错的，大家会找人来责怪。哈，就是你了。

担当责任其实不是那么难的，尤其是当大家心里也有数，不全－是你的错的时候。这带来了担当责任的最好的方式：代人受过。你会因为挑起了担子而心安，那个真正搞砸了的家伙不会成为众矢之的而颓废，至于那个因为你的失职而丢失了半个硬盘的A片的家伙，也会嘟嘟囔囔的承认你至少没有猥猥琐琐的推卸责任。
然后，私下－告诉那个搞砸了的家伙是他搞砸了（如果你能发现他的话）。这样不仅让他以后避免重犯，而且让他知道他欠你一个人情。而且，或许更重要的是，他可能就是那个能修补事故的人。因为，让我们来面对事实，你肯定不行。
担当责任也是最初你来作管理者的原因。这是领导者的本分。大家能信任你，给你荣誉，是因为你在必要的时候能说"是我不好"。而且如果你已经遵循了前面的规则，你现在说这个应该很在行了。

1.2.5. 第五章：禁区
比骂人"猪头"更招人恨的是用挖苦的语调骂人"猪头"。你可以为前一个道歉，后一个你都不会有道歉的机会。即使你其他方面都做的很好，他们可能也不会再听你的了。

我们都自我感觉良好，就是说当别人指手划脚的时候，真的－是可忍孰不可忍。你可能在才智品行上超出你周围所有的人，但是你要不是真的想－招惹谁的话＊，不要"表现"得太明显。类似的，处理问题不要太客气或微妙。客气往往会隔靴搔痒，不得要害。就像人家说的，"在互联网上，没有人听得到你微妙"。大张旗鼓、锣鼓喧天的把你的意见摆出来，不然你没法指望大家领悟到。
一点幽默可以帮助润滑你的蛮横和说教。过分夸张到荒诞的地步，既能充分表达你的观点，又不至于让对方难堪，因为他只会认为你在发疯。这样就可以绕过我们每个人都有的、抵制批评的心理盲区。
＊支一招：和你的工作不直接相关的网络论坛（译者按：Linus是说新闻组。没看到西方国家的论坛事业有中国这么发达。）是发泄的好地方。隔三岔五的，狞笑着写点侮辱人的帖子来点燃战火，会让你再次焕发青春。只是不要把战火烧到自己的老巢。

1.2.6. 第六章：为什么是我？
既然你的主要职责好像就是代人受过，赤裸裸的展示自己如何不称职，显然的问题是：那你为什么还要做呢？
首要的是，可能有也可能没有尖叫着的小女生（或者小男生，我们不要作道学家或性别岐视）来敲你更衣室的门，作"负责人"会－给你带来巨大的个人成就感。不用说你的"领导"其实是拼命从后面追赶大家、努力跟上大家的步伐。每个人还是会认为你是"负责人"。
如果你能驾驭得了，这是一项伟大的工作。
```
读的时候有什么感觉？我读的时候笑了好几次，文章描绘出Linus Torvalds特别搞笑的形象，而且这篇文章的总体意义给我的感觉是**调侃**。

但是，果真如此吗？让我们再看看英文原版：

```
Epilogue
While this book was being prepared for its original publication in Finland, an essay written by Linus Torvalds himself turned up within the files of the Linux source codes. In his essay he explains the management culture that developed over the years in the kernel project. On 10 October 2004, Linus added the file into the Linux kernel sources as a file Documentation/ ManagementStyle and labelled the addition as Wisdom passed down the ages on clay tablets. Hidden within the source codes of the kernel the writing has not received much publicity, but it embodies so much life experience and wisdom, that it should definitely be compulsory reading for any corporate manager. In it we witness the silent nerd turn into a brilliant psychologist and leader, sharing what he has learned while working successfully for 13 years as the project manager for one of the world's largest software projects. And I can't think of a better way to end this book than giving the final word to the master himself.
This is a short document describing the preferred (or made up, depending on who you ask) management style for the linux kernel. It's meant to mirror the CodingStyle document to some degree, and mainly written to avoid answering (*) the same (or similar) questions over and over again.

Management style is very personal and much harder to quantify than simple coding style rules, so this document may or may not have anything to do with reality. It started as a lark, but that doesn't mean that it might not actually be true. You'll have to decide for yourself.
Btw, when talking about "kernel manager", it's all about the technical lead persons, not the people who do traditional management inside companies. If you sign purchase orders or you have any clue about the budget of your group, you're almost certainly not a kernel manager. These suggestions may or may not apply to you.

First off, I'd suggest buying "Seven Habits of Highly Successful People", and NOT read it. Burn it, it's a great symbolic gesture.

(*) This document does so not so much by answering the question, but by making it painfully obvious to the questioner that we don't have a clue to what the answer is.

Anyway, here goes:

Chapter 1: Decisions

Everybody thinks managers make decisions, and that decision-making is important. The bigger and more painful the decision, the bigger the manager must be to make it. That's very deep and obvious, but it's not actually true.

The name of the game is to _avoid_ having to make a decision. In particular, if somebody tells you "choose (a) or (b), we really need you to decide on this", you're in trouble as a manager. The people you manage had better know the details better than you, so if they come to you for a technical decision, you're screwed. You're clearly not competent to make that decision for them.
(Corollary:if the people you manage don't know the details better than you, you're also screwed, although for a totally different reason. Namely that you are in the wrong job, and that _they_ should be managing your brilliance instead).

So the name of the game is to _avoid_ decisions, at least the big and painful ones. Making small and non-consequential decisions is fine, and makes you look like you know what you're doing, so what a kernel manager needs to do is to turn the big and painful ones into small things where nobody really cares.

It helps to realize that the key difference between a big decision and a small one is whether you can fix your decision afterwards. Any decision can be made small by just always making sure that if you were wrong (and you _will_ be wrong), you can always undo the damage later by backtracking. Suddenly, you get to be doubly managerial for making _two_ inconsequential decisions - the wrong one _and_ the right one.

And people will even see that as true leadership (*cough* bullshit *cough*).
Thus the key to avoiding big decisions becomes to just avoiding to do things that can't be undone. Don't get ushered into a corner from which you cannot escape. A cornered rat may be dangerous - a cornered manager is just pitiful.

It turns out that since nobody would be stupid enough to ever really let a kernel manager have huge fiscal responsibility _anyway_, it's usually fairly easy to backtrack. Since you're not going to be able to waste huge amounts of money that you might not be able to repay, the only thing you can backtrack on is a technical decision, and there back-tracking is very easy: just tell everybody that you were an incompetent nincompoop, say you're sorry, and undo all the worthless work you had people work on for the last year. Suddenly the decision you made a year ago wasn't a big decision after all, since it could be easily undone.

It turns out that some people have trouble with this approach, for two reasons:

- admitting you were an idiot is harder than it looks. We all like to maintain appearances, and coming out in public to say that you were wrong is sometimes very hard indeed.

- having somebody tell you that what you worked on for the last year wasn't worthwhile after all can be hard on the poor lowly engineers too, and while the actual _work_ was easy enough to undo by just deleting it, you may have irrevocably lost the trust of that engineer. And remember: "irrevocable" was what we tried to avoid in the first place, and your decision ended up being a big one after all.

Happily, both of these reasons can be mitigated effectively by just admitting up-front that you don't have a friggin' clue, and telling people ahead of the fact that your decision is purely preliminary, and might be the wrong thing. You should always reserve the right to change your mind, and make people very _aware_ of that. And it's much easier to admit that you are stupid when you haven't _yet_ done the really stupid thing.

Then, when it really does turn out to be stupid, people just roll their eyes and say "Oops, he did it again".

This preemptive admission of incompetence might also make the people who actually do the work also think twice about whether it's worth doing or not. After all, if _they_ aren't certain whether it's a good idea, you sure as hell shouldn't encourage them by promising them that what they work on will be included. Make them at least think twice before they embark on a big endeavor.
Remember: they'd better know more about the details than you do, and they usually already think they have the answer to everything. The best thing you can do as a manager is not to instill confidence, but rather a healthy dose of critical thinking on what they do.

Btw, another way to avoid a decision is to plaintively just whine "can't we just do both?" and look pitiful. Trust me, it works. If it's not clear which approach is better, they'll eventually figure it out. The answer may end up being that both teams get so frustrated by the situation that they just give up.

That may sound like a failure, but it's usually a sign that there was something wrong with both projects, and the reason the people involved couldn't decide was that they were both wrong. You end up coming up smelling like roses, and you avoided yet another decision that you could have screwed up on.

Chapter 2: People

Most people are idiots, and being a manager means you'll have to deal with it, and perhaps more importantly, that _they_ have to deal with _you_.

It turns out that while it's easy to undo technical mistakes, it's not as easy to undo personality disorders. You just have to live with theirs - and yours.

However, in order to prepare yourself as a kernel manager, it's best to remember not to burn any bridges, bomb any innocent villagers, or alienate too many kernel developers. It turns out that alienating people is fairly easy, and un-alienating them is hard. Thus "alienating" immediately falls under the heading of "not reversible", and becomes a no-no according to Chapter 1.

There's just a few simple rules here:

(1) don't call people d*ckheads (at least not in public)
(2) learn how to apologize when you forgot rule (1)

The problem with #1 is that it's very easy to do, since you can say "you're a d*ckhead" in millions of different ways (*), sometimes without even realizing it, and almost always with a white-hot conviction that you are right.

And the more convinced you are that you are right (and let's face it, you can call just about _anybody_ a d*ckhead, and you often _will_ be right), the harder it ends up being to apologize afterwards.

To solve this problem, you really only have two options:
- get really good at apologies
- spread the "love" out so evenly that nobody really ends up feeling like they get unfairly targeted. Make it inventive enough, and they might even be amused.

The option of being unfailingly polite really doesn't exist. Nobody will trust somebody who is so clearly hiding his true character.

(*) Paul Simon sang "Fifty Ways to Lose Your Lover", because quite frankly, "A Million Ways to Tell a Developer He Is a D*ckhead" doesn't scan nearly as well. But I'm sure he thought about it.

Chapter 3: People II - the Good Kind

While it turns out that most people are idiots, the corollary to that is sadly that you are one too, and that while we can all bask in the secure knowledge that we're better than the average person (let's face it, nobody ever believes that they're average or below-average), we should also admit that we're not the sharpest knife around, and there will be other people that are less of an idiot that you are.

Some people react badly to smart people. Others take advantage of them.
Make sure that you, as a kernel maintainer, are in the second group. Suck up to them, because they are the people who will make your job easier. In particular, they'll be able to make your decisions for you, which is what the game is all about.

So when you find somebody smarter than you are, just coast along. Your management responsibilities largely become ones of saying "Sounds like a good idea - go wild", or "That sounds good, but what about xxx?". The second version in particular is a great way to either learn something new about "xxx" or seem _extra_ managerial by pointing out something the smarter person hadn't thought about. In either case, you win.

One thing to look out for is to realize that greatness in one area does not necessarily translate to other areas. So you might prod people in specific directions, but let's face it, they might be good at what they do, and suck at everything else. The good news is that people tend to naturally gravitate back to what they are good at, so it's not like you are doing something irreversible when you _do_ prod them in some direction, just don't push too hard.

Chapter 4: Placing blame

Things will go wrong, and people want somebody to blame. Tag, you're it.
It's not actually that hard to accept the blame, especially if people kind of realize that it wasn't _all_ your fault. Which brings us to the best way of taking the blame: do it for another guy. You'll feel good for taking the fall, he'll feel good about not getting blamed, and the guy who lost his whole 36GB porn-collection because of your incompetence will grudgingly admit that you at least didn't try to weasel out of it.

Then make the developer who really screwed up (if you can find him) know _in_private_ that he screwed up. Not just so he can avoid it in the future, but so that he knows he owes you one. And, perhaps even more importantly, he's also likely the person who can fix it. Because, let's face it, it sure ain't you.

Taking the blame is also why you get to be manager in the first place. It's part of what makes people trust you, and allow you the potential glory, because you're the one who gets to say "I screwed up". And if you've followed the previous rules, you'll be pretty good at saying that by now.

Chapter 5: Things to avoid

There's one thing people hate even more than being called "d*ckhead", and that is being called a "d*ckhead" in a sanctimonious voice. The first you can apologize for, the second one you won't really get the chance. They likely will no longer be listening even if you otherwise do a good job.

We all think we're better than anybody else, which means that when somebody else puts on airs, it _really_ rubs us the wrong way. You may be morally and intellectually superior to everybody around you, but don't try to make it too obvious unless you really _intend_ to irritate somebody (*).
Similarly, don't be too polite or subtle about things. Politeness easily ends up going overboard and hiding the problem, and as they say, "On the internet, nobody can hear you being subtle". Use a big blunt object to hammer the point in, because you can't really depend on people getting your point otherwise.

Some humor can help pad both the bluntness and the moralizing. Going overboard to the point of being ridiculous can drive a point home without making it painful to the recipient, who just thinks you're being silly. It can thus help get through the personal mental block we all have about criticism.

(*) Hint: internet newsgroups that are not directly related to your work are great ways to take out your frustrations at other people. Write insulting posts with a sneer just to get into a good flame every once in a while, and you'll feel cleansed. Just don't crap too close to home.

Chapter 6: Why me?

Since your main responsibility seems to be to take the blame for other peoples mistakes, and make it painfully obvious to everybody else that you're incompetent, the obvious question becomes one of why do it in the first place?

First off, while you may or may not get screaming teenage girls (or boys, let's not be judgmental or sexist here) knocking on your dressing room door, you _will_ get an immense feeling of personal accomplishment for being "in charge". Never mind the fact that you're really leading by trying to keep up with everybody else and running after them as fast as you can. Everybody will still think you're the person in charge.

It's a great job if you can hack it.
```
作者的形象、文章的风格和总体意义，是不是完全不一样了？

The most important thing is that it makes us **deep thinking** while reading.

Think about it.




 



