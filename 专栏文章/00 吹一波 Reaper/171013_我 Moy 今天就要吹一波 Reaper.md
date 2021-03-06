我 Moy 今天就来吹一波 Reaper！

接下来我要说的内容，不仅仅是针对音频从业人员，而是针对每一个新时代的媒体工作者、UP主、播客、歌手、程序员、设计师……或者说，任何人。

——只要你想做点和声音相关的事儿（录音、编曲、翻唱、视频配乐等），尽可以用 Reaper 试试。安心，它温柔地像只小绵羊一样，很好上手，用起来很方便，而且功能多到超乎想象。

------

既然开始吹了，来点儿真凭实据，告诉你们为什么 Reaper 值得用。

<接下来开始长篇大论，且配有众多图片。嫌长的请及时关闭，或者扔进收藏然后再也不看就此错过这个神器吧>

不过也有两点警告，需要提前说明：

1. 如果你不爱折腾，你可能不太适合 Reaper——越 Geek 的人越能与它发生共鸣
2. 如果你的英语不好，你大概只能发挥出它 30% 不到的能力（但 Reaper 是有汉化包的）

------

## 一、给视频做声音

（针对人群：UP主、视频编辑等需要对视频声音做处理的人群）

首先，它对视频格式的支持，是所有 DAW 中最完善的。它可以使用 VLC 和 FFMpeg 对视频进行解码处理。这意味着什么？这意味着你再也不用担心每次拖视频进去之后跳出来「文件格式不支持」了！

```
Available decoder information:


========== VLC ==========
VLC v2.2.x
Loaded from: D:\Apps\Reaper\VLC

========== ffmpeg/libav ==========
ffmpeg/libav DLL decoder v54.92.100
Loaded from: D:\Apps\Reaper\Plugins\FFmpeg.dll

========== DirectShow ==========
DirectShow available
```

[VLC](https://www.videolan.org/index.zh.html) 本身就是一个开源的视频播放软件（很好用，尤其是 Mac 端）， 换而言之只要你这个视频软件能支持的格式，Reaper 全都可以吃得下。[FFMpeg](https://www.ffmpeg.org/) 就更不用说了，知名的视频处理库，大部分你用的视频格式转换工具背后都有它的身影（包括B站UP主常用的小丸工具箱）。

视频格式的全面支持是一方面，另一方面它对视频对象的编辑功能也得心应手。

我知道很多同学对「音频软件」的认识就是 Adobe Audition，如果平时有什么视频需要加声音、加音乐也会选择它。诚然，这个软件在国内算是流传度最广的，Adobe 自带大厂保障，有官方中文、使用人群多、教程也全。

但是——它的一个工程只支持一个有效视频。如果拖进去多几个片段，只会有一个片段生效，其他的全都没画面，而且视频的音轨还会另外拆开来。

反观 Reaper 不但没有这种限制，它的视频甚至和普通的声音对象一模一样。你可以拆分、合并、随意拖动任意视频。

![img](https://pic4.zhimg.com/v2-a386acaea142399467ec95311e95490a_b.jpg)

上图中的三个绿色块，就是我把一个视频拆分出来的3个片段。如果交错在一起甚至会自动加入交叉淡化（但是淡化效果不会影响画面，只影响这段视频的声音）。

我想想啊，其他几个“支持视频编辑”的软件，有一个算一个，哪个能这么直接方便地对视频进行操作的？尤其是其中的个别同学（Samplitude、Audition），一次只能支持一个视频，我做5个视频的声音还要开5个工程啊？至于「视频必须放在单独的视频轨里」这种限制我都先不提了，之后再说这方面。

还有一个不算「特性」但是最影响用户体验的因素——流畅度。Reaper 里对视频的编辑非常顺畅，完全不会卡顿。完全，不卡。好，现在到嘲讽 Samplitude 和 Pro Tools 的时间了。你们不但对视频格式一堆要求，而且工程里放个视频就开始全方位影响软件的流畅度，点完播放都要顿个一会儿才播 ，怎么玩？而且这个和配置没关系，至少同等配置下 Reaper 比你们做的好多了！

------

## 二、完全聚合的功能列表

（适用人群：记不住快捷键、经常找不到想要的功能、觉得翻菜单太麻烦的用户）

![img](https://pic1.zhimg.com/v2-32a494232f4c2028be8c2c6a2d715bc5_b.jpg)

给大家介绍一下，这是我们 Reaper 里的神奇海螺：Action List（动作清单）。何谓 Action List？它是一份百科全书，是真理的入口，是万物的起源，是精通所有魔法的终极卷轴。

任何你在 Reaper 软件里能做的操作，小到播放/暂停、拆分、复制、保存，大到 [数据删除] 和 [数据删除]，都会在 Action List 里逐条列出。当你想知道能不能/怎么做某个操作，或者不想翻长长的多级菜单，或者忘了某个快捷键的时候，那就搜一下 Action list 吧！

![img](https://pic4.zhimg.com/v2-2e90019e905b48a5472e70207c2a3ce9_b.jpg)

举一个例子，我们搜最简单的「Play」，可以看到它列出来了我们需要的“播放”功能，并且告诉我们它的快捷键是媒体播放按钮。同时底下还列出来了一些可选项，例如：

1. 播放并跳过当前的时间选区
2. 播放/暂停 （同一个动作在播放的时候是暂停，在暂停的时候是播放）
3. 播放/停止

其他像是「增加播放速率」等等的功能，也一并给你列出来了。

在 Reaper 实际的使用过程中，经常会有「本来只是想要最基础的一架纸飞机，结果赫然在 Action List 中翻出了 13 台隐形昆式战斗机和 5 架高达外加一颗死星」这样的事情发生。

另外，Reaper 是支持「宏」功能的。在某些软件（例如PS）中也叫做「自定义动作」功能，简而言之就是把一系列的操作合并成一步，省去了你重复的劳动。与此同时，它还支持脚本。

对，脚本。编程的脚本。

你可以使用 Lua 语言和Python 语言去给 Reaper 写脚本。

也就是说，像「插入一个轨道，然后把轨道命名成今天的农历日期」或者「把选取的7个对象前后紧贴依次摆好，然后取名叫大娃二娃三娃……七娃，并且把他们额外合并成一个新的声音改名成爷爷然后放到最前面去」这种操作，也都是可以借助脚本实现的哟。

好啦我知道这种奇葩的操作你们会觉得没有意义——我只是想从刁钻的角度出发，让你感受到它能以多么宽广的胸怀包容你的任性。

另外，我真的写出来这个脚本了，见动图：

脚本放在最底下了，没有作假，可以自行感受学习或者验证【笑】

------

快捷的启动速度

对音频插件的兼容支持（64位可以跑32位的）

工程的 Tab 以及子工程功能

所有轨道的通用型，所有对象的一致性

别和我提 Pro Tools，那货光笨重+启动慢+插视频卡顿+要插 iLok 就已经被我打入冷宫了。

抱歉，上文第三段中的斜线句子是骗你们的。它的上手难度类似于语言学习中的C，而且绝不是什么温柔小绵羊。长着羊角的还有一种生物，叫做恶魔。

如果你想用好它，你可能得先花一个星期甚至几个月去熟悉它角角落落的功能，去了解它能做到什么事，去感受怎么样才是最好的契合方式——然后彻底沦为它的信徒。