---
title: Markdown 格式详解与 Solitude 主题 Front Matter 使用说明
date: 2025-06-03 22:14:08
updated: 2025-06-07 20:42:30
cover: https://pic-1.yoxo.top/Canvas-Ruom-7.webp
categories:
  - 教程
tags: 
  - 写作
  - Markdown
  - Solitude
ai_text: 本文提供了 Markdown 语法与 Hexo-Solitude 主题的 Front Matter 使用指南：
  ⒈Markdown核心：
  详解基础语法（标题/列表/代码块）与高级应用（表格/折叠区块/HTML混编）
  ⒉Solitude定制：解析Front Matter配置体系：文章/页面/特色页面的差异化参数（如sticky置顶、ai_test对话框）；分类标签的层次结构实现方案。
  ⒊生产力工具：
  提供在线Markdown编辑器降低使用门槛；附源码下载（CC BY-NC-SA 4.0协议）及合规声明。
  教程突出Solitude Front Matter 功能的扩展性，解决多文档交叉参考痛点，提供主题定制的全链路解决方案。
permalink: post/markdown/   
---
# 前言

Markdown 格式是在（至少是 Hexo 框架下的）个人博客里写作最基本甚至在很多主题下唯一需要掌握的语法了（当然在 Solitude 主题下不是，尤其是如果你要魔改的话），网上的教程也非常多，那为什么我还要写这么一篇文章呢？主要还是因为 Solitude 主题有**外挂标签**这个功能。目前已经有两位大佬都写过外挂标签的使用指南了，但是他们的文章是主要+补充的结构，这就导致我在写文章的时候需要同时参考他们俩的文章再加一篇常规的 Markdown 格式的教程。所以我就想， **为什么不干脆自己写一篇全面的教程呢？**这样我要写文章的时候甚至不用打开浏览器就能直接看到了，~~而且还能水一篇文章~~（事实证明不行，写这个东西累的要命）而且还可能会对大家有帮助。所以，这篇文章就出来啦！

本文分为四个部分： Markdown 简介，Markdown 格式详解，Solitude 主题 Front Matter 使用说明，Solitude 主题内置&外挂标签使用说明。其中 Solitude 主题 Front Matter 使用说明和 Solitude 主题内置&外挂标签使用说明是  Solitude主题独有的，其他主题请自行摸索。我还提供了在线 Markdown 编辑器，供那些懒得学 Markdown 的人使用，在这里你可以像编辑 Word 文档一样编辑文本，编辑器会自动加入 Markdown 格式。当然，还是学学比较好，毕竟技多不压身嘛！

另外再多插一嘴，我本来是想把上面四个部分合在一篇文章里面的，但是写好前面三个部分之后我发现光是这些就已经1124行了，再往下写下去到时候看的时候不方便，所以说我就分成两篇啦！不是我水了两篇文章哦！

OK，坐好扶稳，我们准备发车喽！

#  Markdown 简介

## 什么是 Markdown ？

Markdown 是一种轻量级的标记语言，可以用来在文字中添加格式。Markdown 的开发者 John Gruber，他在 2004 年创建了这种语言。 在 Markdown 中你可以在文本中插入各种符号（见下）来标记格式，渲染器将自动将 Markdown 格式的文档转换成 XHTML 或者 HTML 格式。

Markdown 格式的文档与 Word 之类的文档不同。在 Word 中你需要单击按钮来更改文字的格式，并格式是所见即所得的。但 Markdown  的格式更改一定程度上不是实时可见的。尽管如此，你也不需要担心，有很多（应该说大多数）的 Markdown 编辑器支持让 Markdown 格式的更改可见化，即使你的编辑器不支持显示格式也没有关系，Markdown 的语法本身就是被设计为可读性强且不显眼，所以即使 Markdown 文件中的文本未经过渲染也可以轻松阅读。

>  Markdown 语法的首要设计目标是尽可能易读。基于这个目标, Markdown 格式的文档能够以纯文本形式原样发布，而不会看起来像被填满了标签或格式化指令。 —— John Gruber

一旦你习惯了 Markdown 格式语法，你会发现它甚至在日常的纸面书写中都非常有用。 Markdown 还有一个好处，你可以轻松地仅通过键盘来标记格式，而不用通过鼠标操作从而中断输入，这在高速的文本输入中尤其有用。

## Markdown 可以用来写啥？
### 1. 写网站

这个不用多说了吧？我们写博客文章，页面什么的得用到它，要知道 Markdown 就是为互联网而生的！

### 2. 写文本文件

虽然 Markdown 的功能没有 Word 那么多，但写写作业、信件什么的还是够用哒。用 Markdown 写好内容后，就可以使用 Markdown 文档创作工具来导出为 PDF 或 HTML 格式啦！有了 PDF，就可以打印、发邮件或者传上网啦

### 3. 记笔记

Markdown 简直是最适合原来记笔记的标记语言了！虽然 [Evernote](https://evernote.com)和 [OneNote](https://www.onenote.com)现在还不能直接用Markdown格式创建编辑，都是毕竟还是有一些替代方法的嘛

[Simplenote] 是适用于所有平台的免费、简单的笔记应用程序。
[Notable] 是可以在各种平台上运行的笔记应用程序。
[Bear] 是适用于 Mac 和 iOS 设备的类似 Evernote 的应用程序。默认情况下，它并不专门针对 Markdown 的，但是你可以启用 Markdown 兼容模式。
[Boostnote] 自称是“专为程序员设计的开源笔记应用程序”。

如果你实在离不开Evernote，可以试试 [Marxico](https://marxi.co) ，这是一个专门针对 Evernote 的基于订阅付费的 Markdown编辑器，或在 Evernote 网站上使用 [Markdown Here] 插件。

### 4. 写书

你想自己出书嘛？ 出书可是个比有一个自己的个人博客还酷的事情呢！[Leanpub](https://leanpub.com) 就能把你的 Markdown 变成电子书，PDF,EPUB,MOBI 格式都可以。如果想出纸质书，把 PDF 传到 [Kindle Direct Publishing](https://kdp.amazon.com/) 等服务提供商可以自助出版啦！想了解更多信息可以看看[这篇文章](https://medium.com/techspiration-ideas-making-it-happen/how-i-wrote-and-published-my-novel-using-only-open-source-tools-5cdfbd7c00ca)

### 5. 做PPT

你可能在想：怎么可能用 Markdown 做PPT嘛！但是我真的没骗你，用[Remark](https://remarkjs.com)（[GitHub 仓库](https://github.com/gnab/remark)）和 [Cleaver](https://jdan.github.io/cleaver/)（[GitHub 仓库](https://github.com/jdan/cleaver)）就可以啦用 Markdown 做PPT啦！如果在 Mac 上的话可以用[Deckset](https://www.deckset.com/) 或 [Marked](https://marked2app.com/)。用惯了你就会觉得用 Markdown 比 PowerPoint 或者 Keynote 还好用（听别人说的，不好用别怪我🤪）

### 6. 发邮件

如果你用腻了邮箱自带的排版格式的话，可以试试 [Markdown Here]。它是一个免费、开源的浏览器扩展程序，可以把 Markdown 格式的文本转换成可以发送的 HTML。

### 7. 写技术文档

Markdown 非常适合用来写技术文档，像 GitHub 就已经开始用 Markdown 来写文档了，仓库里的 Readme 文件也是用 Markdown 写哒！

##  Markdown 格式的文件是什么样子的？有哪些软件可以打开它们？

Markdown 格式的文档的拓展名是.md或.markdown。有很多软件可以打开 Markdown 格式的文件，我现在在用的是[Sublime Text](https://www.sublimetext.com/)，这款软件是一款通用文本编辑软件，可以打开很多种格式的文件并支持代码高亮显示。

这篇文章在 Sublime Text 里面看起来是这样的：
![Sublime Text](https://pic-1.yoxo.top/Snipaste_2025-06-06_22-16-28.webp)

下面是在不同平台上可以用的编辑软件：

+ MacOS
[妙言](https://miaoyan.app)
[obsidian](https://obsidian.md)
[Byword](https://bywordapp.com)
[iA Writer](https://ia.com/writer)
[TEXTS](https://texts.io)
[Sublime Text](https://www.sublimetext.com/)

+ Windows
[vscode](https://code.visualstudio.com/w)
[MarkdownPad](https://markdownpad.com)
[TEXTS](https://texts.io)
[Sublime Text](https://www.sublimetext.com/)

+ iOS
[Byword](https://bywordapp.com)
[iA Writer](https://ia.com/writer)

+ 在线编辑器
[markdown](https://markdown.com.cn/editor)
[CodeMirror](https://codemirror.net)
[Dillinger](https://dillinger.io)


## 想了解更多？

可以阅览以下网站：

{% link 'Markdown 入门基础' 'Markdown 教程' 'https://markdown.com.cn/intro.html' %}

{% link 'John Gruber’s Markdown documentation' 'Daring Fireball' 'https://daringfireball.net/projects/Markdown/' %}

↑↑ Markdown 的创建者编写的原始指南

# Markdown 格式详解
## 基本格式
### 标题
要创建标题，请在单词或短语前面添加井号 (#) 。#的数量代表了标题的级别。

``` markdown
# 这是一级标题
## 这是二级标题
### 这是三级标题
#### 这是四级标题
##### 这是五级标题
###### 这是六级标题
```
输出：
<img src="https://pic-1.yoxo.top/Snipaste_2025-06-17_22-34-17.webp" width="250" height="240">

或者也可以通过在文本下方添加任意数量的 == 号来标识一级标题，或者 -- 号来标识二级标题。

``` markdown
这是一级标题
===============
这是二级标题
---------------
```
输出：
<img src="https://pic-1.yoxo.top/Snipaste_2025-06-04_00-07-07.webp" width="200" height="100">

*******************

### 粗体与斜体
#### 粗体
要加粗文本，请在单词或短语的前后各添加两个星号（\*）或下划线（\_）。如需加粗一个单词或短语的中间部分用以表示强调的话，请在要加粗部分的两侧各添加两个星号（\*）。


``` markdown
**生活总要有裂缝，阳光才能照进来。**
__欲买桂花同载酒，终不似、少年游。__
凡是过去，**皆为序章**。
```
输出：
**生活总要有裂缝，阳光才能照进来。**
__欲买桂花同载酒，终不似、少年游。__
凡是过去，**皆为序章**。

*******************

#### 斜体
要用斜体显示文本，请在单词或短语前后添加一个星号（\*）或下划线（\_）。要斜体突出单词的中间部分，请在字母前后各添加一个星号，中间不要带空格。

``` markdown
*凡心所向，素履所往，生如逆旅，一苇以航。*
_夜暗方显万颗星，灯明始见一缕尘。_
万物皆有裂痕，*那是光照进来的地方*。
```
输出：
*凡心所向，素履所往，生如逆旅，一苇以航。*
_夜暗方显万颗星，灯明始见一缕尘。_
万物皆有裂痕，*那是光照进来的地方*。

*******************

#### 粗体与斜体
要同时用粗体和斜体突出显示文本，请在单词或短语的前后各添加三个星号（\*）或下划线（\_）。要加粗并用斜体显示单词或短语的中间部分，请在要突出显示的部分前后各添加三个星号，中间不要带空格。

``` markdown
***还有星月可以寄望，还有宇宙浪漫不止。***
___温柔是黑暗世界里永恒的光。___
__*风停在窗边嘱咐你要热爱这个世界。*__
**_希望你活得尽兴，而不是过得庆幸。_**
慢慢走，***沿途有风景，背后有阳光。***
```
输出：
***还有星月可以寄望，还有宇宙浪漫不止。***
___温柔是黑暗世界里永恒的光。___
__*风停在窗边嘱咐你要热爱这个世界。*__
**_希望你活得尽兴，而不是过得庆幸。_**
慢慢走，***沿途有风景，背后有阳光。***

*******************

#### 粗体嵌套斜体
要使用粗体嵌套斜体，请在要显示粗体单词或短语的前后各添加两个星号（\*）或下划线（\_），并在需要额外显示斜体单词或短语的前后各添加两个星号（\*）

**注意**：如果下划线在内（\*\*粗体\_嵌套\_斜体\*\*或 \_\_\_粗体\_嵌套\_斜体\_\_\_）的话将嵌套将不起作用。

``` markdown
**人在*最无助*的时候，看什么都像救赎**
__如果你为了失去太阳而流泪，*那么你也要失去群星了*__
```
输出：
**人在*最无助*的时候，看什么都像救赎**
__如果你为了失去太阳而流泪，*那么你也要失去群星了*__

*******************

### 删除线
要使用删除线，请在要显示粗体单词或短语的前后各添加一或两个波浪线（\~）

``` markdown
~~服务器繁忙，请稍后再试~~
~真的想不出来啦！~
```
输出：
~~服务器繁忙，请稍后再试~~
~真的想不出来啦！~

*******************

### 引用
#### 单段引用
如果需要引用，请在需要引用的段落前添加一个 > 符号。

``` markdown
> 世界以痛吻我，要我报之以歌。—— 泰戈尔
```
输出：
> 世界以痛吻我，要我报之以歌。—— 泰戈尔

*******************

#### 多段引用
如果需要引用多段，请在空白行中也添加一个 > 符号，这样引用文本就不会被分割成两段。

``` markdown
> 使生如夏花之绚烂，死如秋叶之静美
>
> 我们错看了世界，却说它欺骗了我们。
```
输出：
> 使生如夏花之绚烂，死如秋叶之静美
>
> 我们错看了世界，却说它欺骗了我们。

*******************

#### 嵌套引用
如果你需要嵌套引用，请在要嵌套的段落前添加一个 >> 符号。

``` markdown
> 我做云，你做月亮 。我用两只手遮盖你，我们的屋顶就是青碧的天空。
>
>> —— 泰戈尔《新月集》
```
输出：
> 我做云，你做月亮 。我用两只手遮盖你，我们的屋顶就是青碧的天空。
>
>> —— 泰戈尔《新月集》

*******************

### 列表
#### 无序列表
要创建无序列表，请在每个列表项前面添加破折号 (-)、星号 (\*) 或加号 (+) 。
``` markdown
🧑‍🤝‍🧑出行人员：
+ 孙碧婧
+ 孙碧嫣
+ 高子维
+ 云青珑
+ 云青玲
+ 静莹莹
+ 云朗叔叔
```
输出：
🧑‍🤝‍🧑出行人员：
+ 孙碧婧
+ 孙碧嫣
+ 高子维
+ 云青珑
+ 云青玲
+ 静莹莹
+ 云朗叔叔

*******************

#### 有序列表
要创建有序列表，请在每个列表项前添加数字并紧跟一个英文句点。数字不必按数学顺序排列，但是列表应当以数字 1 开始。

``` markdown
🛒购物清单：
1. 零食，饮料
2. 骑行头盔
3. 工具包
4. 太阳帽
5. 野餐食材
6. 给莹莹买一块新表
```
输出：
🛒购物清单：
1. 零食，饮料
2. 骑行头盔
3. 工具包
4. 太阳帽
5. 野餐食材
6. 给莹莹买一块新表

``` markdown
📦一定要带的东西：
1. 自行车
1. 野餐垫
1. 工具包
1. 相机
1. 背包
```
输出：
📦一定要带的东西：
1. 自行车
1. 野餐垫
1. 工具包
1. 相机
1. 背包

``` markdown
⛰️景点
1. 大王峰
3. 玉女峰
5. 一线天
7. 水帘洞
9. 印象大红袍
```
输出：
⛰️景点
1. 大王峰
7. 玉女峰
0. 一线天
6. 水帘洞
8. 印象大红袍

*******************

#### 嵌套列表
要创建嵌套列表，去在一个列表项下面缩进一个或多个其他列表项。
在嵌套列表项的前面键入空格字符，直至列表标记字符（破折号 (-)、星号 (\*) 或加号 (+)）位于其上方条目中第一个文本字符的正下方。

``` markdown
🥪要采购的食物：
- 零食，饮料
  - 乐事薯片
  - 巧克力
  - 可乐
  - ……
- 野餐食材
  - 三明治
  - 寿司
  - 吐司面包
  - 草莓酱
```
输出：
🥪要采购的食物：
- 零食，饮料
  - 乐事薯片
  - 巧克力
  - 可乐
  - ……
- 野餐食材
  - 三明治
  - 寿司
  - 吐司面包
  - 草莓酱
  - ……

*******************

#### 任务列表

若要创建任务列表，请在列表项前加连字符和空格，后接 \[ \]。 要将任务标记为完成，请使用 \[x\]。

``` markdown
📃时间表：
- [x] 9:00：开车去武夷山景区
- [x] 10:00：爬大王峰
- [ ] 12:00：野餐
- [ ] 13:00：公路骑车
- [ ] 18:00：在市区吃饭
- [ ] 19:00：去看印象大红袍
- [ ] 21:00：回营地
```
输出：
📃时间表：
- [x] 9:00：开车去武夷山景区
- [x] 10:00：爬大王峰
- [ ] 12:00：野餐
- [ ] 13:00：公路骑车
- [ ] 18:00：在市区吃饭
- [ ] 19:00：去看印象大红袍
- [ ] 21:00：回营地

*******************

#### 添加其他元素
要在保留列表连续性的同时在列表中添加另一种元素，请将该元素缩进四个空格。

``` markdown
📝任务：
1. 收集树叶
    收集五种以上不同类型的树叶，把他们裱在相框里
    > 听说每一片叶子都是独一无二的哦！
2. 带走垃圾，留下回忆
    ……
```
输出：
📝任务：
1. 收集树叶
    收集五种以上不同类型的树叶，把他们裱在相框里
    > 听说每一片叶子都是独一无二的哦！
2. 带走垃圾，留下回忆
    ……


*******************

### 代码
要将单词或短语表示为代码，请将其包裹在反引号 (\`) 中。

``` markdown
运行`hexo g`
```

输出：

运行`hexo g`

*******************

### 显示反引号

要在代码块中显示反引号，请将其包在两个个反引号中。

``` markdown
``运行`hexo g` ``
```
输出：
``运行`hexo g` ``

*******************

### 代码块
要将代码或文本格式化为各自的不同块，请将其包裹在三个反引号中。

```` markdown
```
{
  "firstName": "John",
  "lastName": "Smith",
  "age": 25
}
```
````

输出：
```
{
  "firstName": "John",
  "lastName": "Smith",
  "age": 25
}
```

*******************

#### 显示三重反引号
要在代码块中显示三重反引号，请将其包在四个反引号中。

*******************

#### 代码块语法突出显示
许多Markdown处理器都支持受围栏代码块的语法突出显示。使用此功能，您可以为编写代码的任何语言添加颜色突出显示。要添加语法突出显示，请在受防护的代码块之前的反引号旁边指定一种语言。

```` markdown
``` C
#include <stdio.h>

int main() {
    printf("Hello, World!\n");
    return 0;
}
```
````

输出：
``` C
#include <stdio.h>

int main() {
    printf("Hello, World!\n");
    return 0;
}
```

*******************

### 分隔线
要创建分隔线，请在单独一行上使用三个或多个星号 (*\**)、破折号 (---) 或下划线 (_\__) ，并且不能包含其他内容。
以下三种分隔线样式的输出结果都是一样的

``` markdown
***

---

_________________
```
输出：
***

---

_________________


*******************

### 外部链接
#### 创建链接

要创建链接，请将链接文本放在英文的中括号内，链接URL放在后面英文的括号中。

``` markdown
[GitHub官网](https://github.com)
```
输出：
[GitHub官网](https://github.com)

*******************

#### 给链接增加 Title

链接title是当鼠标悬停在链接上时会出现的文字，这个title是可选的，它放在圆括号中链接地址后面，跟链接地址之间以空格分隔。

``` markdown
[Youtube](https://youtube.com "全球最大的视频网站")
```
输出：
[Youtube](https://youtube.com "全球最大的视频网站")

*******************

#### 网址和Email地址

使用尖括号可以很方便地把URL或者email地址变成可点击的链接。

``` markdown
<https://bilibili.com>
<no@thankyou.com>
```
输出：
<https://bilibili.com>
<no@thankyou.com>

或者直接输入URL或者email地址一般也可以直接点击。

``` markdown
https://bilibili.com
no@thankyou.com
```
输出：
https://bilibili.com
no@thankyou.com

如果您不希望自动链接URL，可以通过将URL表示为带反引号的代码或在https后的冒号与@前添加反斜杠 \ 来禁用点击跳转。

``` markdown
https\://bilibili.com
no\@thankyou.com
`https://bilibili.com`
`no@thankyou.com`
```
输出：
https\://bilibili.com
no\@thankyou.com
`https://bilibili.com`
`no@thankyou.com`

*******************

#### 带格式化的链接

要以粗体/斜体显示链接链接, 请在方括号中增加星号。 要将链接表示为代码，请在方括号中添加反引号。

``` markdown
[**知乎**](https://zhihu.com)是一个问答型知识网站
如果想了解更多，请转到[*Markdown 中文教程*](https://markdown.com.cn)
[`node.js`](https://nodejs.org/)
```
输出：
[**知乎**](https://zhihu.com)是一个问答型知识网站
如果想了解更多，请转到[*Markdown 中文教程*](https://markdown.com.cn)
[`node.js`](https://nodejs.org/)

*******************

### 内部链接
#### 网站内部链接

要创建指向本网站某个页面的链接，请将链接文本放在英文的中括号内，去掉域名的链接URL放在后面英文的括号中。

``` markdown
[我的个人简介](/about)
```
输出：
[我的个人简介](/about)

*******************

#### 页面内部链接

要创建指向本页面某个标题的链接，请将链接文本放在英文的中括号内，要跳转的段落放在后面英文的括号中。注意：创建页面内部链接时需要遵循以下规则：
* 字母要转换成小写形式。
* 空格要由连字符 (-) 代替。 任何其他空格或标点符号都要删除。
* 将前导和尾随空格删除。
* 将标记格式删除，只保留内容（例如，_italics_ 变为 italics）。
* 如果标题的自动生成的定位点与同一文档中的早期定位点相同，那么要通过追加连字符和自动递增整数来生成唯一标识符。

示例：
``` markdown
# Example headings

## Sample Section

## This'll be a _Helpful_ Section About the Greek Letter Θ!
A heading containing characters not allowed in fragments, UTF-8 characters, two consecutive spaces between the first and second words, and formatting.

## This heading is not unique in the file

TEXT 1

## This heading is not unique in the file

TEXT 2

# Links to the example headings above

Link to the sample section: [Link Text](#sample-section).

Link to the helpful section: [Link Text](#thisll-be-a-helpful-section-about-the-greek-letter-Θ).

Link to the first non-unique section: [Link Text](#this-heading-is-not-unique-in-the-file).

Link to the second non-unique section: [Link Text](#this-heading-is-not-unique-in-the-file-1).
```

``` markdown
[Markdown 格式](#markdown-格式)
```
输出：
[Markdown 格式](#markdown-格式)

*******************

### 图片
#### 普通图片

要添加图像，请使用英文感叹号 (!), 然后在方括号增加说明文本，图片链接放在圆括号里。

``` markdown
![上海-外滩](https://pic-1.yoxo.top/china-7094961_1280.webp)
```
输出：
![上海-外滩](https://pic-1.yoxo.top/china-7094961_1280.webp)

*******************

#### 链接图片

给图片增加链接，请普通图片链接括在方括号中，然后将要跳转的地址添加在圆括号中。

``` markdown
[![使用Vercel部署博客](https://pic-1.yoxo.top/Canvas-Ruom-4.webp)](/post/solitude-reinventing)
```
输出：
[![使用Vercel部署博客](https://pic-1.yoxo.top/Canvas-Ruom-4.webp)](/post/solitude-reinventing)

*******************

### 表格
可以使用竖线 | 和连字符 - 创建表。 连字符用于创建每列的标题，而竖线用于分隔每列。 必须在表格前包含空白行，以便其正确呈现。
``` markdown
| 第一个标题 | 第二个标题 |
|------------|------------|
| 第一格     | 第二格     |
| 第一格     | 第二格     |
| 第一格     | 第二格     |
```
输出：
| 第一个标题 | 第二个标题 |
|------------|------------|
| 第一格     | 第二格     |
| 第一格     | 第二格     |
| 第一格     | 第二格     |

单元格的宽度可以不同，无需在列内准确对齐，但是标题行的第一列中必须至少有三个横线。

``` markdown
| 第一个标题         |   第二个标题 |
|---|------------|
| 第一格 | 第二格           |
| 第一格    |    第二格    |
| 第一格        | 第二格            |
```
输出：
| 第一个标题         |   第二个标题 |
|---|------------|
| 第一格 | 第二格           |
| 第一格    |    第二格    |
| 第一格        | 第二格            |

如果要给整个表格添加一个标题的话，请在上面再添加一个只有标题的表格，并与下面的表格空出一行的距离。

``` markdown
|         总标题         |
| --------------------- |

| 第一个标题 | 第二个标题 |
|------------|------------|
| 第一格     | 第二格     |
| 第一格     | 第二格     |
| 第一格     | 第二格     |
```
输出：
|         总标题         |
| --------------------- |

| 第一个标题 | 第二个标题 |
|------------|------------|
| 第一格     | 第二格     |
| 第一格     | 第二格     |
| 第一格     | 第二格     |

如果你觉得这样做表太不方便，可以使用这个网站：[Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables)，在里面你可以像常规制表一样制作你的表格，然后获得表格的Markdown格式。

*******************

### 定义列表
一些Markdown处理器允许您创建术语及其对应定义的定义列表。要创建定义列表，请在第一行上键入术语。在下一行，键入一个冒号，后跟一个空格和定义。
``` markdown
C++
: C++（c plus plus）是一种计算机高级程序设计语言，由C语言扩展升级而产生，最早于1979年由本贾尼·斯特劳斯特卢普在AT&T贝尔工作室研发。 
```
输出：
C++
: C++（c plus plus）是一种计算机高级程序设计语言，由C语言扩展升级而产生，最早于1979年由本贾尼·斯特劳斯特卢普在AT&T贝尔工作室研发。

******************* 

### 表情符号

你可以直接输入或从 [Emojipedia](https://emojipedia.org/) 等来源复制表情符号并将其粘贴到文档中，或按快捷键{% keyboard Windows %} + {% keyboard . %}使用 Windows 系统自带的表情符号。

*******************

### 忽略 Markdown 格式

要显示原本用于格式化 Markdown 文档的字符，请在字符前面添加反斜杠字符 \ 。

``` markdown
输入密码后请按\*号开门
```
输出：
输入密码后请按\*号开门

*******************

### Markdown 内嵌 HTML 标签

对于 Markdown 涵盖范围之外的标签，都可以直接在文件里面用 HTML 本身。如需使用 HTML，不需要额外标注这是 HTML 或是 Markdown，只需 HTML 标签添加到 Markdown 文本中即可。

``` html
<del>怎么跑出来一个奇奇怪怪的东西</del>
<strong>快看快看！</strong>
```
输出：
<del>怎么跑出来一个奇奇怪怪的东西</del>
<strong>快看快看！</strong>

*******************

## 变通方法
### 前言

大多数使用Markdown的人会发现，基础语法和扩展语法已能满足需求。但如果您长期使用Markdown，可能会发现某些必要功能确实缺失。本段提供了一些绕过Markdown限制的技巧。针对Markdown官方不支持的某些功能的替代解决方案。

*******************

### 下划线

Markdown 原生不支持下划线，可能是因为网页文本中的下划线通常表示超链接。然而，在写论文或报告时，可能需要使用下划线。如果你在 Markdown 中需要使用下划线，可以使用 \<ins\> 标签

``` html
<ins>星河滚烫，人间理想。</ins>
```
输出：
<ins>星河滚烫，人间理想。</ins>

*******************

### 上/下标

Markdown 原生不支持上/下标，如果你在 Markdown 中需要使用上/下标，可以使用 \<sup\>和\<sub\> 标签
``` html
这是<sup>上标</sup>文本
这是<sub>下标</sub>文本
```
输出：
这是<sup>上标</sup>文本
这是<sub>下标</sub>文本

*******************

### 缩进

Markdown 里的空格和制表符有特殊用途，比如创建换行或代码块。如果你想缩进段落，可以尝试以下方法：

``` html
&nbsp;&nbsp;&nbsp;&nbsp;风停了，云在等月亮。
```
输出：
&nbsp;&nbsp;&nbsp;&nbsp;风停了，云在等月亮。

*******************

### 文字居中

Markdown 没有文本对齐的语法，但可以使用CSS 解决：

``` html
<p style="text-align:center">夜深了，星星还醒着。</p>
```
输出：
<p style="text-align:center">夜深了，星星还醒着。</p>

*******************

### 文字颜色

Markdown 不支持更改文字颜色，但 HTML 可以：

``` html
<font color="red">这段文字是红色的！</font>
<p style="color:blue">这段文字是蓝色的。</p>
```
输出：
<font color="red">这段文字是红色的！</font>
<p style="color:blue">这段文字是蓝色的。</p>

*******************

### 警告框

Markdown 没有警告框功能，但可以使用引用块（>）+ Emoji + 加粗模拟：

``` markdown
> ⚠️ **警告：** 不要按下大红色按钮！

> 📝 **注意：** 日出很美。

> 💡 **提示：** 记得珍惜生活中的小事。
```
输出：
> ⚠️ **警告：** 不要按下大红色按钮！

> 📝 **注意：** 日出很美。

> 💡 **提示：** 记得珍惜生活中的小事。

*******************

### 注释

Markdown 没有内置的注释功能，但可以使用一种非官方的方法：

``` markdown
这是可见的段落。

[这是一个隐藏的注释]: # 

这是另一个可见的段落。
```
输出：
这是可见的段落。

[这是一个隐藏的注释]: # 

这是另一个可见的段落。

*******************

### 调整图片大小

Markdown 不能指定图片尺寸，但可以用 HTML 设定宽高。双引号内加图片链接。
``` html
<img src="https://pic-1.yoxo.top/cat-323262_1280.webp" width="200" height="100">
```
输出：
<img src="https://pic-1.yoxo.top/cat-323262_1280.webp" width="200" height="100">
图片将以 200x100 像素显示。

*******************

### 表格格式

Markdown 不能直接在表格中换行或插入列表，但可以用 HTML 解决：

*******************

#### 表格内换行

``` markdown
| 第一个标题 | 第二个标题 |
|------------|------------|
| 第一段<br><br>第二段   | 第一段<br><br>第二段 |
```
输出：
| 第一个标题 | 第二个标题 |
|------------|------------|
| 第一段<br><br>第二段   | 第一段<br><br>第二段 |

*******************

#### 表格内列表

``` markdown
| 第一个标题 | 第二个标题 |
|------------|------------|
|<ul><li>项目一</li><li>项目二</li></ul> | <ul><li>项目一</li><li>项目二</li></ul> |
```
输出：
| 第一个标题 | 第二个标题 |
|------------|------------|
|<ul><li>项目一</li><li>项目二</li></ul> | <ul><li>项目一</li><li>项目二</li></ul> |

*******************

### 折叠信息

可以通过创建读者可以选择展开的折叠部分来暂时隐藏 Markdown 的内容。 

要创建折叠部分，可以使用\<details\> 标签。使用\<summary\> 标签让读者知道里面的内容。 

``` html
<details>
<summary>龙应台《目送》</summary>
华安上小学第一天，我和他手牵着手，穿过好几条街，到维多利亚小学。九月初，家家户户院子里的苹果和梨树都缀满了拳头大小的果子，枝丫因为负重而沉沉下垂，越出了树篱，钩到过路行人的头发。
　　很多很多的孩子，在操场上等候上课的第一声铃响。小小的手，圈在爸爸的、妈妈的手心里，怯怯的眼神，打量着周遭。他们是幼儿园的毕业生，但是他们还不知道一个定律：一件事情的毕业，永远是另一件事情的开启。
　　铃声一响，顿时人影错杂，奔往不同方向，但是在那么多穿梭纷乱的人群里，我无比清楚地看着自己孩子的背影──就好像在一百个婴儿同时哭声大作时，你仍旧能够准确听出自己那一个的位置。华安背着一个五颜六色的书包往前走，但是他不断地回头；好像穿越一条无边无际的时空长河，他的视线和我凝望的眼光隔空交会。
　　我看着他瘦小的背影消失在门里。
　　十六岁，他到美国做交换生一年。我送他到机场。告别时，照例拥抱，我的头只能贴到他的胸口，好像抱住了长颈鹿的脚。他很明显地在勉强忍受母亲的深情。
　　他在长长的行列里，等候护照检验；我就站在外面，用眼睛跟着他的背影一寸一寸往前挪。终于轮到他，在海关窗口停留片刻，然后拿回护照，闪入一扇门，倏忽不见。
　　我一直在等候，等候他消失前的回头一瞥。但是他没有，一次都没有。
　　现在他二十一岁，上的大学，正好是我教课的大学。但即使是同路，他也不愿搭我的车。即使同车，他戴上耳机──只有一个人能听的音乐，是一扇紧闭的门。有时他在对街等候公交车，我从高楼的窗口往下看：一个高高瘦瘦的青年，眼睛望向灰色的海；我只能想象，他的内在世界和我的一样波涛深邃，但是，我进不去。一会儿公交车来了，挡住了他的身影。车子开走，一条空荡荡的街，只立着一只邮筒。
　　我慢慢地、慢慢地了解到，所谓父女母子一场，只不过意味着，你和他的缘分就是今生今世不断地在目送他的背影渐行渐远。你站立在小路的这一端，看着他逐渐消失在小路转弯的地方，而且，他用背影默默告诉你：不必追。
</details>
```
输出：
<details>
<summary>龙应台《目送》</summary>
华安上小学第一天，我和他手牵着手，穿过好几条街，到维多利亚小学。九月初，家家户户院子里的苹果和梨树都缀满了拳头大小的果子，枝丫因为负重而沉沉下垂，越出了树篱，钩到过路行人的头发。
　　很多很多的孩子，在操场上等候上课的第一声铃响。小小的手，圈在爸爸的、妈妈的手心里，怯怯的眼神，打量着周遭。他们是幼儿园的毕业生，但是他们还不知道一个定律：一件事情的毕业，永远是另一件事情的开启。
　　铃声一响，顿时人影错杂，奔往不同方向，但是在那么多穿梭纷乱的人群里，我无比清楚地看着自己孩子的背影──就好像在一百个婴儿同时哭声大作时，你仍旧能够准确听出自己那一个的位置。华安背着一个五颜六色的书包往前走，但是他不断地回头；好像穿越一条无边无际的时空长河，他的视线和我凝望的眼光隔空交会。
　　我看着他瘦小的背影消失在门里。
　　十六岁，他到美国做交换生一年。我送他到机场。告别时，照例拥抱，我的头只能贴到他的胸口，好像抱住了长颈鹿的脚。他很明显地在勉强忍受母亲的深情。
　　他在长长的行列里，等候护照检验；我就站在外面，用眼睛跟着他的背影一寸一寸往前挪。终于轮到他，在海关窗口停留片刻，然后拿回护照，闪入一扇门，倏忽不见。
　　我一直在等候，等候他消失前的回头一瞥。但是他没有，一次都没有。
　　现在他二十一岁，上的大学，正好是我教课的大学。但即使是同路，他也不愿搭我的车。即使同车，他戴上耳机──只有一个人能听的音乐，是一扇紧闭的门。有时他在对街等候公交车，我从高楼的窗口往下看：一个高高瘦瘦的青年，眼睛望向灰色的海；我只能想象，他的内在世界和我的一样波涛深邃，但是，我进不去。一会儿公交车来了，挡住了他的身影。车子开走，一条空荡荡的街，只立着一只邮筒。
　　我慢慢地、慢慢地了解到，所谓父女母子一场，只不过意味着，你和他的缘分就是今生今世不断地在目送他的背影渐行渐远。你站立在小路的这一端，看着他逐渐消失在小路转弯的地方，而且，他用背影默默告诉你：不必追。
</details>

*******************

### 插入视频

Markdown 不能直接嵌入视频，但可以使用 HTML：
``` html
<iframe height="400" width="600" src="//player.bilibili.com/player.html?aid=49775093&cid=87150521&page=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe>
```
输出：
<iframe height="400" width="600" src="//player.bilibili.com/player.html?aid=49775093&cid=87150521&page=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe>

*******************

## Markdown 格式生成器
对于那些懒得学 Markdown 的人，我在这里为你准备了两个 Markdown 格式生成器~~（看我人多好）~~你可以在左边那个栏里面像使用Word一样使用生成器来编辑文档，然后在右边那个栏里面查看或者复制 Markdown 格式的文本。
{% link '菜鸟工具' 'Markdown 在线编辑器' 'https://www.jyshare.com/front-end/712/' %}
{% link '锤子工具' 'Markdown 在线编辑' 'https://www.toolhelper.cn/Code/Markdown' %}

# Front Matter
## 简介
Front Matter 是位于 HTML/Markdown 文件顶部的 YAML 或 JSON 代码块，用于配置写作设置。通常包括封面、摘要、目录等内容。

以 YAML 格式书写时，Front-matter 以三个破折号结束；以 JSON 格式书写时，Front-matter 以三个分号结束：

``` yaml
---
title: Hello World
date: 2013/7/13 20:46:25
---
```
``` json
"title": "Hello World",
"date": "2013/7/13 20:46:25"
;;;
```
## Solitude 主题 Front Matter 使用说明

在显示为不同类型（文章、页面、特色页面）的 Markdown 文件中 Front Matter 所包含的内容是不同的。下面是在这三种Markdown 文件中 Front Matter 包含的内容。

{% tabs Front Matter %}
<!-- tab 文章 -->
``` yaml
---
title:
date:
updated:
tags:
categories:
permalink:
comment:
cover:
katex:
reprint:
locate:
sticky:
ai_test:
---
```
<!-- endtab -->
<!-- tab 页面 -->
``` yaml
---
title:
date:
updated:
type:
comment:
desc:
cover:
katex:
aside:
---
```
<!-- endtab -->
<!-- tab 特色页面（即刻、工具箱、我的装备、豆瓣页（音乐、图书、游戏））-->
```yaml
---
leftend:
rightend:
rightbtn:
rightbtnlink:
---
```
<!-- endtab -->
{% endtabs %}

以下为各值代表的内容以及默认值：

| 属性 | 值类型 | 是否必须 | 解释 | 默认值 |
| ---- | ----- | -------- | ---- | ---- |
| title    | 文字 | 必需 | 文章/页面标题 | 文章的文件名 |
| date     | 日期 | 必需 | 文章/页面创建日期 | 文件建立日期 |
| updated  | 日期 | 可选 | 文章/页面更新日期 | 文件更新日期 |
| tags     | 文字 | 可选 | 文章标签 | 
| categories | 文字 | 可选 | 文章分类 |
| permalink | URL | 可选 | 覆盖文章的永久链接，应该以 / 或 .html 结尾 |
| type     | 文字 | 特殊页面必须 | 特殊页面类型 | 
| desc     | 文字 | 可选 | 页面描述 |
| aside    | true/false | 可选 | 是否开启侧边栏| true |
| comment  | true/false | 可选 | 显示文章/页面评论模块| true |
| cover    | URL  | 可选 | 文章封面图片URL |
| reprint  | true/false | 可选 | 版权（默认为原创）为true时为转载 |
| katex    | true/false | 可选 | 显示 katex| false |
| locate   | 文字 | 可选 | 文章创作地点 |
| leftend  | 文字 | 可选 | banner底部左侧文字 |
| rightend | 文字 | 可选 | banner底部右侧文字 |
| rightbtn | 文字 | 可选 | banner底部右侧按钮文字 |
| rightbtnlink | 文字 | 可选 |  banner底部右侧按钮跳转链接 |
| container| true/false  | 可选 | 是否开启容器| true |
| sticky   | 数字 | 可选 | 设置文章置顶，其中较高的数字代表着较高的排序 |
| ai_test  | 文字 | 可选 | ai 框里面输入的文本 |

## 分类和标签的说明

只有文章支持分类和标签。 分类按顺序应用于文章，从而形成分类和子分类的层次结构。 标签是在相同的层次结构上定义的，因此它们的出现顺序不重要。

示例
``` yaml
categories:
  - Sports
  - Baseball
tags:
  - Injury
  - Fight
  - Shocking
```

# 下载源码

这篇文章也是用 Markdown 格式写哒，如果你想查看本篇文章的源码的话，可以点击下面的按钮下载下来看看哦~

{% button 'fab fa-markdown' 'Markdown 格式' 'https://files.zohopublic.com.cn/public/workdrive-public/download/9kwj71263a960c58f4b47850995bff69abbf2?x-cli-msg=%7B%22linkId%22%3A%221GtE4MoQcsx-35P3d%22%2C%22isFileOwner%22%3Afalse%2C%22version%22%3A%221.0%22%2C%22isWDSupport%22%3Afalse%7D' %}
{% button 'fas fa-file-lines' 'TXT 格式' 'https://files.zohopublic.com.cn/public/workdrive-public/download/9kwj758b913f12e4f493ea0fdf7e60ca0a335?x-cli-msg=%7B%22linkId%22%3A%221GtE4MoQcsy-35P3d%22%2C%22isFileOwner%22%3Afalse%2C%22version%22%3A%221.0%22%2C%22isWDSupport%22%3Afalse%7D' %}

另外请注意：由于本篇文章是通过CC BY-NC-SA 4.0协议共享的，如果你下载了源码的话，也请遵守CC BY-NC-SA 4.0协议的各项规定哦~

您可以：

+ 自由使用：您可以在任何媒介以任何形式复制、发行本作品。
+ 自由更改：您可以任意修改、转换或以本作品为基础进行创作。

您必须：

+ 署名：表明本文来自本站。
+ 非商业性使用：您不得将本作品用于商业目的。
+ 以相同方式共享：您使用本文时也需要按照CC BY-NC-SA 4.0协议贡献您的作品。

需要更多信息，请浏览Creative Commons官网对CC BY-NC-SA 4.0协议的介绍：https://creativecommons.org/licenses/by-nc-sa/4.0/deed.zh-hans

# 参考文章
{% fold 参考文章 %}
{% tabs 参考文章 %}
<!-- tab Markdown 简介 -->
{% link 'Markdown 入门基础' 'Markdown 教程' 'https://markdown.com.cn/intro.html' %}
{% link 'Markdown' ' 百度百科' 'https://baike.baidu.com/item/markdown/3245829' %}
{% link '什么是Markdown？为什么需要使用Markdown？' '知乎' 'https://zhuanlan.zhihu.com/p/150583965' %}
<!-- endtab -->
<!-- tab Markdown 格式 -->
{% link 'Markdown 基本语法' 'Markdown 教程' 'https://markdown.com.cn/basic-syntax/' %}
{% link 'Markdown 拓展语法' 'Markdown 教程' 'https://markdown.com.cn/extended-syntax/' %}
{% link 'Markdown 语法变通' 'Markdown 教程' 'https://markdown.com.cn/hacks.html' %}
{% link '基本撰写和格式语法' 'GitHub 文档' 'https://docs.github.com/zh/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax#further-reading' %}
{% link '使用高级格式' 'GitHub 文档' 'https://docs.github.com/zh/get-started/writing-on-github/working-with-advanced-formatting' %}
<!-- endtab -->
<!-- tab Front Matter -->
{% link 'Front-matter' 'Hexo' 'https://hexo.io/zh-cn/docs/front-matter' %}
{% link 'Front Matter' 'Solitude 文档' 'https://solitude.js.org/guide/front-matter.html' %}
<!-- endtab  -->
{% endtabs %}
{% endfold %}