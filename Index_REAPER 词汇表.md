# 新手必备！REAPER 词汇表

## 为什么要做这个？

我希望做成一个工具书，而不仅仅是“小词典”。
我希望你们通过它，除了知道“这个单词的中文”是什么，还可以知道它在 DAW 中通常的作用，一点简单的解释。

毕竟很多单词，你仅仅知道中文也基本没有帮助，需要结合实例讲解才能有更直观的概念。

## 小学英语

这部分单词属于小学英语的范畴，有点基础的都可以直接跳过。

File：文件

New：新建

Open：打开

Save：保存

Save As：另存为

Edit：编辑

View：视图

Project：工程

Previous：前一个

Next：下一个

Show：显示，通常在 Action List 里和某某窗口联用，如 Show Video Window 即显示视频窗口。

Hide：隐藏，和 Show 相对应。

Windows：窗口，Floating Window 指浮动窗口；Docked 则是指固定在界面上的的窗口。

Set：设置、设定

Insert：插入，常见于 Insert Track 插入新轨道。

Add：增加

Delete：删除

Remove：移除，和 Delete 类似

Time：时间

Start：开始、起点

End：结束点、终点

Current：当前的

Load：加载

Audio：音频

Video：视频

---

## 软件基础概念

### 轨道

Track：轨道，REAPER 中只有一种类型的轨道，视频、音频（单双声道）和 Midi 都可以一视同仁地摆在相同轨道上。

Track Folder：轨道文件夹，一个轨道中可以放入多个子轨道。所有的子轨道都受轨道文件夹的属性和效果器影响，相当于默认的 BUS 轨。
轨道文件夹有三种收缩状态，便于不同的查看需求。

Master：总轨，Master Track，所有轨道的声音都会经由这条总轨输出。也就是你对 Master 添加的效果器会对所有声音生效。

Mix：混音。

### 路由

Route：路由，你可以理解为信号的通道关系。没错，和“路由器”的路由是同一个意思。在 DAW 中通常指代不同轨道和音频的信号走向。“发送”之类的操作都是通过 Route 来实现的。

Send：发送，将一个轨道的音频信号发送到另一个轨道。通常来说相当于“在另一个轨道上复制了一份声音”。不过也存在串联的发送关系，例如 Track Folder（轨道文件夹）内的子轨道的信号都会发送到父级轨道，而所有轨道的声音都会发送到 Master Track（总线轨）。
之所有所发送操作通常是为了额外添加效果器，来达到干湿声混合的效果。有时候也会把多个轨道发送到同一个接收轨，并添加统一的效果器来做整体处理。

Receive：接收，和发送对应，作为接受音频信号的一方。

AUX：辅助轨。一种特殊的 Receiver Track，用来做额外一层声音处理。如大量歌曲中的混响都是使用的辅助轨。

BUS：总线轨。Master Track 就是最大的 BUS 轨。单向的发送关系，由下至上一层层单向发送。

Channel：通道，解释起来也相当复杂。简单粗暴理解的话，就……“左右声道”是两个“通道”，这样的通道。

---

### 自动化

Automation：自动化。让某个参数（如音量）自动变化的操作。可以通过边操作边录制自动化的包络线，或者手动画包络线来实现。你可以理解为自动化是“操作”，而包络线是自动化后的一种“结果”。

Automation Mode：自动化模式，常见的有 Read、Touch、Latch、Write 等模式。
> 可以查看[REAPER 中的自动化操作解析](link)

Envelope：包络线，自动化控制使用的线段。自动化会读取包络的线段对参数进行调节。例如你画一条从低到高的音量包络线，那么受影响的声音就会从轻到响逐渐变化；而如果你画一条上下抖动的声像包络线，那声音就会忽左忽右地变化。

Envelope Point：包络点，基本是和 Envelope 一起出现的，指包络线上的一个节点。

Note：在软件里通常有两种意思，音符（通常和midi一起出现），或者备注（Item Note）

Media：媒体

### 效果器

Fx：效果器/插件，其实是 Effects（效果）的简写

VST：虚拟工作室技术，也就是常见的“插件”、“效果器”的一种格式。类似的还有 AU、AAX 等格式的插件。

FX Chain：效果链，即一串的效果器。也可以理解为插件链。

Presets：预设，通常在效果器中会有各种预设，即实现存好的一套或多套配置，供反复调用。

### REAPER 特有概念

REAPEAR：死神/镰刀，本软件的简写。全称是：Rapid Environment for Audio Production Engineering, and Recording（针对音频生产、工程学以及录音的极速环境），正规写法是全大写字母。
顺便一提，昵称是「瑞破」或者「莉啪（娘化？）」。

**Item：** 缺少完全准确的中文单词。勉强可以作“对象”理解。你在 REAPER 里看到的所有“音频块”就是一个个的 Item，每个 Item 内还可以包含多个 Take。根据 Item 的内容，还可以细分为：Empty Item、Text Item（写了备注的空对象）、Midi Item，还有最常见的音频 Item 和视频 Item。
> 关于空对象，可以查看这篇文章：[有趣的空对象](link)

**Take：** 缺少完全准确的中文单词。勉强作为“选块”理解吧。你可以通过 Implode 操作将多个 Item 合为一个具有多个 Take 的新 Item。鼠标点击 Take 可以激活它，只有被激活的 Take 会被播放，其他 Take 不出声。
通常用在多次录制（挑选最好的一次）或是随机样本中。
*顺便一提，在属性设置中可以选择针对某个 Item，同时播放所有的 Take。这个用法比较少见。*

Comp：缺少完全准确的中文单词。暂且理解成“Take组”吧，多个 Item 的 Take 的某种固定组合。

Lane：缺少完全准确的中文单词。姑且理解为“栏”，或者“跑道”。

Free Item Position Track：自由对象位置轨道。

Sub-Project：子工程。

Toolbar：工具栏

Script：脚本

### 标记

Marker：标记

Region：区域

### 属性相关

Property：属性，复数 Properties。每个 Item 都有各自的属性，你可以点开 Item Properties 查看诸如音量、声像、名称、通道数等信息。

Pitch：音调

Volume：音量

Pan：声像

Solo：独奏

Mute：静音

Position：位置

Length：长度

Name：名称

Loop：循环

Loop Section：循环区间，指 Item 中循环播放的一段区域。默认不开启。

Phase：相位。相对而言是个不那么重要的概念。

Peak：波峰，常和 Waveform 联用。

Lock：锁定

Mono：单声道

Stereo：立体声

## 音乐相关

Midi：就……Midi？全称是 Musical Instrument Digital Interface，一两句说不清楚，反正就是软件里用来记录音符各项数据用的一种载体。

CC：Control ，通常和 MIDI 联用

VSTi：虚拟乐器，或者说是“音源”。

Beat：节拍

BPM：Beat per Minute，每分钟节拍数。通常可以代表一首歌的快慢。

Timebase：时基。

Measure：小节

Tempo：节奏

Import：导入

Export：导出，和 Render 渲染类似

Grid：网格

Snap：吸附

Snap Offset：吸附偏移

Group：组、集合

Editor：编辑器

Source：来源，通常指媒体源文件

Fade：淡化效果，如 Fade In 淡入，Fade out 淡出，CrossFade 交叉淡化

Curve：曲线，通常用 Fade Curve 来代表淡化曲线的形状。

Stretch：拉伸；特有概念 Stretch Marker 指拉伸记号，用于在一段音频内调节时间伸缩的效果。

Action：动作/操作；RP 中有 Action List 动作列表（也可以叫操作清单）窗口，包含了几乎软件内所有可执行的操作。
> 关于 Action List 可以查看[万能的动作列表](link)

## 操作相关

Edge：边缘，通常指 Item 两侧的部分。

Move：移动

Mouse：鼠标

Mouse Wheel：鼠标滚轮

Cursor：指针，可以细分为 Play Cursor 播放指针和 Edit Cursor 编辑指针

Play Cursor：播放指针

Select：选择，若为 Selected 则指是选中的状态，如 Selected Items 为所有选中的对象。

### 状态

Arm：装载，通常在软件里指「激活/预备某种状态」，如轨道的 Record Arm 指“做好录音的准备”——接下来录制的内容会被录到这条轨道上。

Disarm：卸载，和 Arm 对应。可以理解为取消激活。

Enable：启用，比如 FX enabled 即效果器正常启用的状态。

Disable：禁用，比如 FX disabled 即将效果器都暂时禁用，也就是听到不经过效果器处理的原始声音。

Bypass：旁通。通常是针对效果器，临时“忽略”掉单个效果器的作用。可以用来对比前后效果。和 Disable FX 相比，Bypass 通常是针对单个效果器，而 Disable FX 是针对整个效果链。

### 走带

Transport：走带控制，在 DAW 里通常指代那个放置「播放、暂停、录音」等等按钮的区域。最早应该是来源于老式录音机吧？播放啊、暂停啊，“让录音带走走停停”，走带，这么个意思。

Play：播放

Pause：暂停，写作 Play/Pause 的动作即切换播放/暂停的状态。

Stop：停止，和暂停的区别在于，Pause 时播放指针会停在当前播放到的位置，而 Stop 将直接返回到开始播放的时间点。

Record：录音/录制，走带控制的那个红色大按钮就是录音按钮。

Repeat：重复，很多时候和 Loop 可以换用。

## 设置相关

Default：默认

Custom：自定义

Toggle：切换，通常是针对某些能开关的对象，例如本来是开启（On）的窗口，你 Toggle 它一下，它就变成关闭（Off）了，反之亦然。

Option：选项，有时也用 Preference。在 REAPER 的 Option 菜单中，你可以快速更改某些设定（例如录音模式、走带模式以及基础的吸附、组操作等等）。

Use：使用；User 则代表用户，

Mode：模式

Ignore：忽略

### 设备和输入输出

Input：输入

Output：输出，与 Input（输入）对应

Device：设备


