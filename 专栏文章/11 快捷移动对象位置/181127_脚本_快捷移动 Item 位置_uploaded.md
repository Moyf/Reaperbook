# 音效师超实用操作——REAPER 技巧：快速移动 Item

嗨，大家好，欢迎收看写给音效师和广播剧后期的 REAPER 指南。

本期介绍的是特别实用的两个小功能，可以让你 **如臂使指般** 操作选中的对象——例如将它们快速移动到鼠标下方。
这对于每天面对数十个甚至上百个 Item 的音效师来说会是非常实用的操作技巧。

效果如下图所示：

![1 最终效果small](https://i.loli.net/2019/04/12/5cb0088cc2a86.gif)

这次先放视频，然后是惯例的图文教程。

​    

---



 好，接下来是图文部分~

首先回顾一下上面的动图，图中有这两个操作：

1. 将 Item 移动到鼠标所在时间（横向位移）
2. 将 Item 移动到鼠标所指向的轨道上（纵向位移）

如何做到这两件事呢？

非常简单：**自定义动作（Custom Action）**

所谓的自定义动作，其实就是「将几个动作组合在一起，形成新的动作」。具体设置方法可以查看视频，之后我也会专门出一篇文章详细介绍自定义动作，这次就先直接用起来吧~



## 其一： 如何将 Item 移到鼠标指针所指向的时间？（不变更轨道）

拆解开来看，这个操作包含了两个基础动作：

1. 将 Edit Cursor 移动到鼠标指针所在的时间点
2. 将 Item 移动到 Edit Cursor 所在的时间点

![1554996195443](https://i.loli.net/2019/04/12/5cb0088fcb363.png)

之所以这么多此一举，是因为不存在直接将 Item 移动到鼠标（Mouse Cursor）位置的动作，所以需要曲线救国哈。



## 其二：如何将 Item 移到鼠标所在的轨道？（不变更时间）

拆解开来看，这个操作包含了两个基础动作：

1. 选中鼠标下方的轨道
2. 使用脚本将 Item 移动到选中的轨道
3. （可选）对 Free Item Positioning Track 的 Item 重新排列位置，避免相互重叠

> 点击这里下载脚本：[me2beats_Move item s to selected track.lua](<https://raw.githubusercontent.com/Moyf/Reaperbook/master/%E4%B8%93%E6%A0%8F%E6%96%87%E7%AB%A0/11%20%E5%BF%AB%E6%8D%B7%E7%A7%BB%E5%8A%A8%E5%AF%B9%E8%B1%A1%E4%BD%8D%E7%BD%AE/me2beats_Move%20items%20to%20selected%20track.lua>)
> （在链接上右键→另存为）

![1554996225234](https://i.loli.net/2019/04/12/5cb008928afc1.png)

基本原理和之前的一样，就不另行解释了。



之所以有第三个可选的动作，是为了实现以下效果：

![190410_@0032](https://i.loli.net/2019/04/12/5cb0089630728.gif)

这个动作只对 FIPT（Free Item Positioning Track，自由对象位置轨道）有效，作用就是让 Item 可以有条理地摆放整齐。

如果你平时不用 FIPT 轨道，那么可以不加第三个动作。



## 其三：如何将 Item 直接移动到鼠标所在的位置？

机智的你肯定想到了：新建一个自定义动作，并把上面两个动作拖入即可。

没错：**自定义动作之间可以再次嵌套**。

![1554996044317](https://i.loli.net/2019/04/12/5cb0089911b21.png)

这样就可以一次性让选中的对象（Selected Item）完全移到鼠标所在的位置。



为什么有一步到位的方法，我还要拆开3个自定义动作呢？

因为有的时候，我**需要同时移动多个 Item 的时间，但不希望他们合并到同个轨道上**——这时候，划分细致的动作就提供了更多的自由度。



## 拓展：将「移动」改为「复制」操作

如果想要将 Item「复制到鼠标所在的位置」，应该怎么做呢？

很简单，在 Custom Action 的最开始加一个 Item: Duplicate Items （复制选中的对象）就可以。

![img](https://i.loli.net/2019/04/12/5cb0089bb4ea1.jpg)

效果如下：

![33f5d148-33bf-4dc1-8d90-ddbd9fb55fd2](https://i.loli.net/2019/04/12/5cb0089e7ba72.gif)

以上，这就是本期 REAPER 实用技巧的分享。



---



## 拓展阅读：

[什么是 Action List](https://zhuanlan.zhihu.com/p/55308791)

[如何用脚本交换选中的两个对象所在的轨道](https://zhuanlan.zhihu.com/p/30126094)



---



P.S. 如果下载脚本遇到问题，可直接复制以下内容，创建一个文本文档，保存成 lua 后缀名即可。
如：`move_item_to_selected_track.lua`

``` lua
-- @description Move items to selected track
-- @version 1.0
-- @author me2beats
-- @changelog
--  + init

local r = reaper; local function nothing() end; local function bla() r.defer(nothing) end

local items = r.CountSelectedMediaItems() if items == 0 then bla() return end

tr = r.GetSelectedTrack(0,0)  if not tr then bla() return end

t = {}
for i = 0, items-1 do
  local item = r.GetSelectedMediaItem(0,i)
  t[#t+1] = item
end

r.Undo_BeginBlock()
for i = 1,#t do r.MoveMediaItemToTrack(t[i], tr) end
r.UpdateArrange()
r.Undo_EndBlock('Move items to sel track', -1)

```

