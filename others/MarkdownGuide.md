# Markdown-学习指南

## 目录 {#content}

[TOC]


## 1. 导语

>   Markdown 是一种轻量级标记语言，创始人为约翰·格鲁伯（John Gruber）。Markdown的目的是希望大家“使用易读易写的纯文本格式编写文档，然后转换成有效的XHTML(或者HTML)文档”[^1]。该语言也吸收了很多在电子邮件中已有的纯文本标记的特性。


## 2. 区块元素[^2]

### 2.1 段落和换行

一个 Markdown 段落是由一个或多个连续的文本行组成，它的前后要有一个以上的空行（空行的定义是显示上看起来像是空的，便会被视为空行。比方说，若某一行只包含空格和制表符，则该行也会被视为空行）。普通段落不该用空格或制表符来缩进。

### 2.2 标题

Markdown 支持两种标题的语法。类 Setext 和类 atx 形式。

1.类 Setext 形式是用底线的形式，利用 = （最高阶标题）和 - （第二阶标题），任何数量的 = 和 - 都可以有效果。例如：

```
    This is an H1
    =============

    This is an H2
    -------------
```

2.类 Atx 形式则是在行首插入 1 到 6 个 # ，对应到标题 1 到 6 阶。例如：
 
```   
    # 这是 H1

    ## 这是 H2

    ###### 这是 H6
```

### 2.3 区块引用

Markdown中的区块引用是在引用的行或者段落前面加 >。
在每一行前面加 >:

```
> This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
> consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
> Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.
> 
> Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
> id sem consectetuer libero luctus adipiscing.
```

在整个段落前面加 >:

```
> This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.

> Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
id sem consectetuer libero luctus adipiscing.
```

区块引用可以嵌套（例如：引用内的引用），只要根据层次加上不同数量的 > ：

```
> This is the first level of quoting.
>
> > This is nested blockquote.
>
> Back to the first level.
```

引用的区块内也可以使用其他的 Markdown 语法，包括标题、列表、代码区块等：

```
> ## 这是一个标题。
> 
> 1.   这是第一行列表项。
> 2.   这是第二行列表项。
> 
> 给出一些例子代码：
> 
>     return shell_exec("echo $input | $markdown_script");
```

### 2.4 列表

Markdown 支持有序列表和无序列表。

无序列表使用星号、加号或是减号作为列表标记：

```
*   Red
*   Green
*   Blue
```

等同于：

```
+   Red
+   Green
+   Blue
```

也等同于：

```
-   Red
-   Green
-   Blue
```

有序列表则使用数字接着一个英文句点：

```
1.  Bird
2.  McHale
3.  Parish
```

很重要的一点是，你在列表标记上使用的数字并不会影响输出页面数字的正确性。例如下面两个有序列表的输出页面相同。

```
1.  Bird
1.  McHale
1.  Parish
```

```
1.  Bird
2.  McHale
3.  Parish
```

如果列表项目间用空行分开，在输出时会分为两段。下面的 Markdown 就会产生两段：

```
*   Bird

*   Magic
```

在行首出现数字-句点-空白，要避免这样的状况，你可以在句点前面加上反斜杠。

```
1986\. What a great season.
```

### 2.5 代码区块

和程序相关的写作或是标签语言原始码通常会有已经排版好的代码区块，通常这些区块我们并不希望它以一般段落文件的方式去排版，而是照原来的样子显示。

插入程序代码的方式有两种，一种是利用缩进(Tab), 另一种是利用 ` 符号（一般在ESC键下方）包裹代码。

* 要在 Markdown 中利用缩进(Tab)建立代码区块很简单，只要简单地缩进 4 个空格或是 1 个制表符就可以，这个每行一阶的缩进（4 个空格或是 1 个制表符），都会被移除。一个代码区块会一直持续到没有缩进的那一行（或是文件结尾）。例如，下面的输入：

```
这是一个普通段落：

    这是一个代码区块。
```

* 另一种建立代码区块的方法是用 ` 符号包裹。
1.  插入行内代码，即插入一个单词或者一句代码的情况，使用 `code` 这样的形式插入。 
2.  如果要插入插入块代码，你可以用多个反引号( \`\`\` )来开启和结束代码区段。在多个 \` 符号之后( \`\`\`Java )， 可以制定具体语言的代码。

``````
\`\`\`
public static void main(String[] args) {
    
}
\`\`\`
``````

### 2.6 分隔线

你可以在一行中用三个以上的星号、减号、底线来建立一个分隔线，行内不能有其他东西。你也可以在星号或是减号中间插入空格。下面每种写法都可以建立分隔线。

```
* * *

***

*****

- - -

---------------------------------------
```

### 2.7 表格[^3]

简单方式写表格：

```
    学号|姓名|分数
    -|-|-
    小明|男|75
    小红|女|79
    小陆|男|92
```

原生方式写表格：

```
    |学号|姓名|分数|
    |-|-|-|
    |小明|男|75|
    |小红|女|79|
    |小陆|男|92|
```

为表格第二列指定方向：

```
    产品|价格
    -|-:
    Leanote 高级账号|60元/年
    Leanote 超级账号|120元/年
```

**注：**

   * 不管是哪种方式，第一行为表头，第二行分隔表头和主体部分，第三行开始每一行为一个表格行。
   * 列于列之间用管道符|隔开。原生方式的表格每一行的两边也要有管道符。
   * 第二行还可以为不同的列指定对齐方向。默认为左对齐，在-右边加上:就右对齐。




### 2.8 内容目录

在段落中填写 [TOC] 以显示全文内容的目录结构。

```
[TOC]
```


## 3 区段元素[^2]

### 3.1 链接

Markdown 支持两种形式的链接语法： 行内式和参考式两种形式。不管是哪一种，链接文字都是用 [] 来标记。

* 行内式
要建立一个行内式的链接，只要在方块括号后面紧接着圆括号并插入网址链接即可，如果你还想要加上链接的 title 文字，只要在网址后面，用双引号把 title 文字包起来即可，例如：

```
This is [an example](http://example.com/ "Title") inline link.

[This link](http://example.net/) has no title attribute.
```

如果你是要链接到同样主机的资源，你可以使用相对路径：

```
See my [About](/about/) page for details.
```

* 参考式

参考式的链接是在链接文字的括号后面再接上另一个方括号，而在第二个方括号里面要填入用以辨识链接的标记：

```
This is [an example][id] reference-style link.
```

你也可以选择性地在两个方括号中间加上一个空格：

```
This is [an example] [id] reference-style link.
```

接着，在文件的任意处，你可以把这个标记的链接内容定义出来：

```
[id]: http://example.com/  "Optional Title Here"
```

链接内容定义的形式为：

   * 方括号（前面可以选择性地加上至多三个空格来缩进），里面输入链接文字
   * 接着一个冒号
   * 接着一个以上的空格或制表符
   * 接着链接的网址
   * 选择性地接着 title 内容，可以用单引号、双引号或是括弧包着

下面这三种链接的定义都是相同：

```
[foo]: http://example.com/  "Optional Title Here"
[foo]: http://example.com/  'Optional Title Here'
[foo]: http://example.com/  (Optional Title Here)
```

**请注意：**有一个已知的问题是 Markdown.pl 1.0.1 会忽略单引号包起来的链接 title。

链接网址也可以用 <> 包起来：

```
[id]: <http://example.com/>  "Optional Title Here"
```

你也可以把 title 属性放到下一行，也可以加一些缩进，若网址太长的话，这样会比较好看：

```
[id]: http://example.com/longish/path/to/resource/here
    "Optional Title Here"
```

网址定义只有在产生链接的时候用到，并不会直接出现在文件之中。

链接辨别标签可以有字母、数字、空白和标点符号，但是并不区分大小写，因此下面两个链接是一样的：

```
[link text][a]
[link text][A]
```

隐式链接标记功能让你可以省略指定链接标记，这种情形下，链接标记会视为等同于链接文字，要用隐式链接标记只要在链接文字后面加上一个空的方括号，如果你要让 "Google" 链接到 google.com，你可以简化成：

```
[Google][]
```

然后定义链接内容：

```
[Google]: http://google.com/
```

由于链接文字可能包含空白，所以这种简化型的标记内也许包含多个单词：

```
Visit [Daring Fireball][] for more information.
```

然后接着定义链接：

```
[Daring Fireball]: http://daringfireball.net/
```

链接的定义可以放在文件中的任何一个地方，我比较偏好直接放在链接出现段落的后面，你也可以把它放在文件最后面，就像是注解一样。

下面是一个参考式链接的范例：

```
I get 10 times more traffic from [Google] [1] than from
[Yahoo] [2] or [MSN] [3].

  [1]: http://google.com/        "Google"
  [2]: http://search.yahoo.com/  "Yahoo Search"
  [3]: http://search.msn.com/    "MSN Search"
```

如果改成用链接名称的方式写：

```
I get 10 times more traffic from [Google][] than from
[Yahoo][] or [MSN][].

  [google]: http://google.com/        "Google"
  [yahoo]:  http://search.yahoo.com/  "Yahoo Search"
  [msn]:    http://search.msn.com/    "MSN Search"
```

使用 Markdown 的参考式链接，可以让文件更像是浏览器最后产生的结果，让你可以把一些标记相关的元数据移到段落文字之外，你就可以增加链接而不让文章的阅读感觉被打断。

### 3.2 锚点[^3]

网页中，锚点其实就是页内超链接，也就是链接本文档内部的某些元素，实现当前页面中的跳转。比如我这里写下一个锚点，点击回到目录，就能跳转到目录。 

在目录中点击这一节，就能跳过来。还有下一节的注脚。这些根本上都是用锚点来实现的。

在你准备跳转到的指定标题后插入锚点{#标记}，然后在文档的其它地方写上连接到锚点的链接。

```
    ## 0. 目录{#index}
    跳转到[目录](#index)
```

**注意：**
   1. Markdown Extra 只支持在标题后插入锚点，其它地方无效。
   2. Leanote 编辑器右侧显示效果区域暂时不支持锚点跳转，所以点来点去发现没有跳转不必惊慌，但是你发布成笔记或博文后是支持跳转的。
   
### 3.3 注脚[^3]

在需要添加注脚的文字后加上脚注名字[^注脚名字],称为加注。 然后在文本的任意位置(一般在最后)添加脚注，脚注前必须有对应的脚注名字。

```
使用 Markdown[^1]可以效率的书写文档, 直接转换成 HTML[^2], 你可以使用 Leanote[^Le] 编辑器进行书写。
[^1]:Markdown是一种纯文本标记语言
[^2]:HyperText Markup Language 超文本标记语言
[^Le]:开源笔记平台，支持Markdown和笔记直接发为博文
```

### 3.4 强调

Markdown 使用星号（*）和底线（_）作为标记强调字词的符号，被 * 或 _ 包围的字词会被转成用 <em> 标签包围，用两个 * 或 _ 包起来的话，则会被转成 <strong>，例如：

```
*single asterisks*

_single underscores_

**double asterisks**

__double underscores__
```

你可以随便用你喜欢的样式，唯一的限制是，你用什么符号开启标签，就要用什么符号结束。

强调也可以直接插在文字中间：

```
un*frigging*believable
```

但是如果你的 * 和 _ 两边都有空白的话，它们就只会被当成普通的符号。

如果要在文字前后直接插入普通的星号或底线，你可以用反斜线：

```
\*this text is surrounded by literal asterisks\*
```

### 3.5 图片

很明显地，要在纯文字应用中设计一个「自然」的语法来插入图片是有一定难度的。

Markdown 使用一种和链接很相似的语法来标记图片，同样也允许两种样式： 行内式和参考式。

行内式的图片语法看起来像是：

```
![Alt text](/path/to/img.jpg)

![Alt text](/path/to/img.jpg "Optional title")
```

详细叙述如下：

   * 一个惊叹号 !
   * 接着一个方括号，里面放上图片的替代文字
   * 接着一个普通括号，里面放上图片的网址，最后还可以用引号包住并加上 选择性的 'title' 文字。

参考式的图片语法则长得像这样：

```
![Alt text][id]
```
[id] 是图片参考的名称，图片参考的定义方式则和连结参考一样：

```
[id]: url/to/image  "Optional title attribute"
```

到目前为止， Markdown 还没有办法指定图片的宽高，如果你需要的话，你可以使用普通的 <img> 标签。


## 4 其它

### 4.1 自动链接

Markdown 支持以比较简短的自动链接形式来处理网址和电子邮件信箱，只要是用方括号包起来， Markdown 就会自动把它转成链接。一般网址的链接文字就和链接地址一样，例如：

```
<http://example.com/>
```

### 4.2 HTML 原始码[^3]

在代码区块里面， & 、 < 和 > 会自动转成 HTML 实体，这样的方式让你非常容易使用 Markdown 插入范例用的 HTML 原始码，只需要复制贴上，剩下的 Markdown 都会帮你处理，例如：

```
<div class="footer">
   © 2004 Foo Corporation
</div>
```

输出为：
<div class="footer">
   © 2004 Foo Corporation
</div>

```
<table>
    <tr>
        <th rowspan="2">值班人员</th>
        <th>星期一</th>
        <th>星期二</th>
        <th>星期三</th>
    </tr>
    <tr>
        <td>李强</td>
        <td>张明</td>
        <td>王平</td>
    </tr>
</table>
```

输出为：

<table>
    <tr>
        <th rowspan="2">值班人员</th>
        <th>星期一</th>
        <th>星期二</th>
        <th>星期三</th>
    </tr>
    <tr>
        <td>李强</td>
        <td>张明</td>
        <td>王平</td>
    </tr>
</table>

### 4.3 LaTeX 公式[^3]

* $ 表示行内公式
   
```
质能守恒方程可以用一个很简洁的方程式 $E=mc^2$ 来表达。
```

* $$ 表示整行公式

```
$$\sum_{i=1}^n a_i=0$$
```

### 4.4 流程图[^3]

```
flow
st=>start: Start:>https://www.zybuluo.com
io=>inputoutput: verification
op=>operation: Your Operation
cond=>condition: Yes or No?
sub=>subroutine: Your Subroutine
e=>end
st->io->op->cond
cond(yes)->e
cond(no)->sub->io
```

## 参考文件

[^1]: Markdown 1.0.1 Introduction. [Daring Fireball - Markdown](http://daringfireball.net/projects/markdown/ "Markdown"). 17-Dec-2004.
[^2]: [Markdown 语法说明（简体中文版）](http://www.appinn.com/markdown/) 
[^3]: [Markdown-语法手册（完整整理版）](http://blog.leanote.com/post/freewalk/Markdown-语法手册)


