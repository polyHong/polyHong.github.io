---
layout: post
title: Markdown基本语法
category: 技术
tags: Markdown
keywords: Markdown
description: Markdown basic syntax
---


>约翰·格鲁伯设计文档中概述的Markdown元素。

## 标题

使用 `#` 创建标题，注意`#`符号的数量应与标题级别相对应。 例如，要创建标题级别三，需要使用三个`#`符号（例如 `### My Header` ）。

| Markdown | HTML | 渲染输出 |
| --- | --- | --- |
| `# Heading level 1` | `<h1>Heading level 1</h1>` | # 标题等级1 |
| `## Heading level 2` | `<h2>Heading level 2</h2>` | ## 标题等级2 |
| `### Heading level 3` | `<h3>Heading level 3</h3>` | ### 标题级别3 |
| `#### Heading level 4` | `<h4>Heading level  4</h4>` | #### 标题级别4 |
| `##### Heading level 5` | `<h5>Heading level 5</h5>` | ##### 标题5 |
| `###### Heading level 6` | `<h6>Heading level 6</h6>` | ###### 标题等级6 |

### 替代语法

或者，在文本下方的行上，添加任意数量的 `==` 标题级别1的 `--` 字符 或 标题级别2的字符。

| Markdown | HTML | 渲染输出 |
| --- | --- | --- |
| `Heading level 1   ===============` | `<h1>Heading level 1</h1>` | # 标题等级1 |
| `Heading level 2   ---------------` | `<h2>Heading level 2</h2>` | ## 标题等级2 |

## 段落

创建段落，使用空白行分隔一行或多行文本。 不应缩进带有空格或制表符的段落。

| Markdown | HTML | 渲染输出 |
| --- | --- | --- |
| `            I really like using Markdown.                 I think I'll use it to format all of my documents from now on.          ` | `<p>I really like using Markdown.</p>               <p>I think I'll use it to format all of my documents from now on.</p>` | 我真的很喜欢使用Markdown。  我想从现在开始，我将使用它来格式化所有文档。 |

## 换行

要创建换行符（ `<br>` ），以两个或多个空格结束一行，然后键入return。

| Markdown | HTML | 渲染输出 |
| --- | --- | --- |
| `            This is the first line.               And this is the second line.          ` | `<p>This is the first line.<br>            And this is the second line.</p>` | 这是第一行。   这是第二行。 |

## 着重

可以通过使文本变为粗体或斜体来增加着重。

### 粗体

要加粗文本，在单词或短语的前后添加两个星号或下划线。 加粗一个单词的中部以强调，在字母周围添加两个星号，且各空格之间不加空格。

| Markdown | HTML | 渲染输出 |
| --- | --- | --- |
| `I just love **bold text**.` | `I just love <strong>bold text</strong>.` | 我只喜欢 **粗体字** 。 |
| `I just love __bold text__.` | `I just love <strong>bold text</strong>.` | 我只喜欢 **粗体字** 。 |
| `Love**is**bold` | `Love<strong>is</strong>bold` | 爱 **是** 大胆的 |

### 斜体

要斜体显示文本，在单词或短语的前后添加一个星号或下划线。 要斜体突出单词的中间部分，在字母周围添加一个星号，中间不要带空格。

| Markdown | HTML | 渲染输出 |
| --- | --- | --- |
| `Italicized text is the *cat's meow*.` | `Italicized text is the <em>cat's meow</em>.` | 斜体文字是 *猫的叫声* 。 |
| `Italicized text is the _cat's meow_.` | `Italicized text is the <em>cat's meow</em>.` | 斜体文字是 *猫的叫声* 。 |
| `A*cat*meow` | `A<em>cat</em>meow` | 一个 *猫* 喵 |

### 粗体和斜体

同时突出显示带有粗体和斜体的文本，在单词或短语的前后添加三个星号或下划线。

| Markdown | HTML | 渲染输出 |
| --- | --- | --- |
| `This text is ***really important***.` | `This text is <strong><em>really important</em></strong>.` | 这段文字 ***真的很重要*** 。 |
| `This text is ___really important___.` | `This text is <strong><em>really important</em></strong>.` | 这段文字 ***真的很重要*** 。 |
| `This text is __*really important*__.` | `This text is <strong><em>really important</em></strong>.` | 这段文字 ***真的很重要*** 。 |
| `This text is **_really important_**.` | `This text is <strong><em>really important</em></strong>.` | 这段文字 ***真的很重要*** 。 |

## 块引用

创建blockquote，在段落前面添加一个`>` 。

```
> Dorothy followed her through many of the beautiful rooms in her castle.
```

呈现的输出如下所示：

> Dorothy followed her through many of the beautiful rooms in her castle.

### 具有多个段落的块引用

块引用可以包含多个段落。 在段落之间的空白行上添加一个`>`。

```
> Dorothy followed her through many of the beautiful rooms in her castle.
>
> The Witch bade her clean the pots and kettles and sweep the floor and keep the fire fed with wood.
```

呈现的输出如下所示：

> Dorothy followed her through many of the beautiful rooms in her castle.
>
> The Witch bade her clean the pots and kettles and sweep the floor and keep the fire fed with wood.

### 嵌套块引用

块引用可以嵌套。在要嵌套的段落前面添加一个`>>`。

```
> Dorothy followed her through many of the beautiful rooms in her castle.
>
>> The Witch bade her clean the pots and kettles and sweep the floor and keep the fire fed with wood.
```

呈现的输出如下所示：

> Dorothy followed her through many of the beautiful rooms in her castle.
>
>> The Witch bade her clean the pots and kettles and sweep the floor and keep the fire fed with wood.

### 具有其他元素的块引用

块引用可以包含其他Markdown格式的元素。 并非所有元素都可以使用-您需要进行实验以查看哪些元素有效。

```
> #### The quarterly results look great!
>
> - Revenue was off the chart.
> - Profits were higher than ever.
>
>  *Everything* is going according to **plan**.
```

呈现的输出如下所示：

> #### The quarterly results look great!
>
> - Revenue was off the chart.
> - Profits were higher than ever.
>
>  *Everything* is going according to **plan**.

## 清单

可以将项目组织成有序和无序列表。

### 有序列表

创建有序列表，在订单项中添加数字和句点。 数字不必按数字顺序排列，但列表应以数字开头。

| Markdown | HTML | 渲染输出 |
| --- | --- | --- |
| `          1. First item           2. Second item           3. Third item           4. Fourth item        ` | `          <ol>             <li>First item</li>             <li>Second item</li>             <li>Third item</li>             <li>Fourth item</li>           </ol>        ` | 1. 第一项 2. 第二项 3. 第三项 4. 第四项 |
| `            1. First item             1. Second item             1. Third item             1. Fourth item          ` | `            <ol>               <li>First item</li>               <li>Second item</li>               <li>Third item</li>               <li>Fourth item</li>             </ol>          ` | 1. 第一项 2. 第二项 3. 第三项 4. 第四项 |
| `            1. First item             8. Second item             3. Third item             5. Fourth item          ` | `            <ol>               <li>First item</li>               <li>Second item</li>               <li>Third item</li>               <li>Fourth item</li>             </ol>          ` | 1. 第一项 2. 第二项 3. 第三项 4. 第四项 |
| `            1. First item             2. Second item             3. Third item                 1. Indented item                 2. Indented item             4. Fourth item          ` | `            <ol>               <li>First item</li>               <li>Second item</li>               <li>Third item                 <ol>                   <li>Indented item</li>                   <li>Indented item</li>                 </ol>               </li>               <li>Fourth item</li>             </ol>          ` | 1. 第一项 2. 第二项 3. 第三项 	1. 缩进项 	2. 缩进项 4. 第四项 |

### 无序列表

创建无序列表，在订单项前添加破折号（ `-` ），星号（ `*` ）或加号（ `+` ）。 缩进一个或多个项目以创建嵌套列表。

| Markdown | HTML | 渲染输出 |
| --- | --- | --- |
| `            - First item             - Second item             - Third item             - Fourth item          ` | `            <ul>               <li>First item</li>               <li>Second item</li>               <li>Third item</li>               <li>Fourth item</li>             </ul>          ` | - 第一项 - 第二项 - 第三项 - 第四项 |
| `            * First item             * Second item             * Third item             * Fourth item          ` | `            <ul>               <li>First item</li>               <li>Second item</li>               <li>Third item</li>               <li>Fourth item</li>             </ul>          ` | - 第一项 - 第二项 - 第三项 - 第四项 |
| `            + First item             * Second item             - Third item             + Fourth item          ` | `            <ul>               <li>First item</li>               <li>Second item</li>               <li>Third item</li>               <li>Fourth item</li>             </ul>          ` | - 第一项 - 第二项 - 第三项 - 第四项 |
| `            - First item             - Second item             - Third item                 - Indented item                 - Indented item             - Fourth item          ` | `            <ul>               <li>First item</li>               <li>Second item</li>               <li>Third item                 <ul>                   <li>Indented item</li>                   <li>Indented item</li>                 </ul>               </li>               <li>Fourth item</li>             </ul>          ` | - 第一项 - 第二项 - 第三项 	- 缩进项 	- 缩进项 - 第四项 |

### 在列表中添加元素

要在保留列表连续性的同时在列表中添加另一个元素，将该元素缩进四个空格或一个制表符，如以下示例所示。

#### 段落

```
*   This is the first list item.
*   Here's the second list item.

    I need to add another paragraph below the second list item.

*   And here's the third list item.
```

呈现的输出如下所示：

*   This is the first list item.
*   Here's the second list item.

    I need to add another paragraph below the second list item.

*   And here's the third list item.


#### 块引用

```
*   This is the first list item.
*   Here's the second list item.

    > A blockquote would look great below the second list item.

*   And here's the third list item.
```

呈现的输出如下所示：

*   This is the first list item.
*   Here's the second list item.

    > A blockquote would look great below the second list item.

*   And here's the third list item.


#### 代码块

[代码块](https://markdown.p2hp.com/basic-syntax/index.html#code-blocks) 通常缩进四个空格或一个制表符。 当它们在列表中时，将它们缩进八个空格或两个选项卡。

```
1.  Open the file.
2.  Find the following code block on line 21:

        <html>
          <head>
            <title>Test</title>
          </head>

3.  Update the title to match the name of your website.
```

呈现的输出如下所示：

1.  Open the file.
2.  Find the following code block on line 21:

        <html>
          <head>
            <title>Test</title>
          </head>

3.  Update the title to match the name of your website.


#### 图片

```
1.  Open the file containing the Linux mascot.
2.  Marvel at its beauty.

    ![Tux, the Linux mascot](/assets/images/tux.png)

3.  Close the file.
```

呈现的输出如下所示：

1.  Open the file containing the Linux mascot.
2.  Marvel at its beauty.
    ![Tux，Linux吉祥物](https://d33wubrfki0l68.cloudfront.net/e7ed9fe4bafe46e275c807d63591f85f9ab246ba/e2d28/assets/images/tux.png)
3.  Close the file.


## 代码

要将单词或短语表示为代码，将其括在勾号（ `` ` `` ）中。

| Markdown | HTML | 渲染输出 |
| --- | --- | --- |
| ``At the command prompt, type `nano`.`` | `At the command prompt, type <code>nano</code>. ` | 在命令提示符下，键入 `nano` 。 |

### 转义刻度线

如果要表示为代码的单词或短语包含一个或多个刻度线，可以通过将单词或短语括在双刻度线（ ` `` ` ）中来对其进行转义 。

| Markdown | HTML | 渲染输出 |
| --- | --- | --- |
| ``` ``Use `code` in your Markdown file.`` ``` | ``<code>Use `code` in your Markdown file.</code>`` | ``Use `code` in your Markdown file.`` |

### 代码块

要创建代码块，在代码块的每一行缩进至少四个空格或一个制表符。

```
<html>
      <head>
      </head>
    </html>
```

呈现的输出如下所示：

```
<html>
  <head>
  </head>
</html>
```

## 水平线

要创建水平线 `***`，单独在一行上使用三个或更多的星号（ ），破折号（ `---` ）或下划线（ `___` ）。

```
***

---

_________________
```

所有这三个的渲染输出看起来都相同：

---

## 链接

要创建链接，将链接文本括在方括号（例如 `[Duck Duck Go]` ）中，然后立即在URL后面加上括号（例如 `(https://duckduckgo.com)` ）中的URL 。

```
My favorite search engine is [Duck Duck Go](https://duckduckgo.com).
```

呈现的输出如下所示：

我最喜欢的搜索引擎是 [Duck Duck Go](https://duckduckgo.com/) 。

### 添加标题

可以选择为链接添加标题。 当用户将鼠标悬停在链接上时，这将显示为工具提示。 要添加标题，将其括在URL后面的括号中。

呈现的输出如下所示：

我最喜欢的搜索引擎是 [Duck Duck Go](https://duckduckgo.com/ "最好的隐私搜索引擎") 。

### 网址和电子邮件地址

要将URL或电子邮件地址快速转换为链接，将其括在尖括号中。

```
<https://markdown.p2hp.com>
<fake@example.com>
```

呈现的输出如下所示：

[https://markdown.p2hp.com](https://markdown.p2hp.com/index.html)  
[fake@example.com](https://markdown.p2hp.com/basic-syntax/)

### 格式化链接

为了 [强调](https://markdown.p2hp.com/basic-syntax/index.html#emphasis) 链接，在方括号和括号之前和之后添加星号。

```
I love supporting the **[EFF](https://eff.org)**.
This is the *[Markdown Guide](https://markdown.p2hp.com)*.
```

呈现的输出如下所示：

我喜欢支持 **[EFF](https://eff.org/)** 。  
这是《 *[Markdown指南》](https://markdown.p2hp.com/index.html)* 。

### 参考样式链接

引用样式链接是一种特殊的链接，它使URL在Markdown中更易于显示和阅读。 引用样式的链接分为两部分：与文本保持内联的部分以及在文件中其他位置存储的部分，以使文本易于阅读。

#### 格式化链接的第一部分

参考样式链接的第一部分使用两组括号进行格式化。 第一组方括号包围应显示为链接的文本。 第二组括号显示了一个标签，该标签用于指向您存储在文档其他位置的链接。

尽管不是必需的，但您可以在第一组和第二组支架之间包含一个空格。 第二组括号中的标签不区分大小写，可以包含字母，数字，空格或标点符号。

这意味着以下示例格式对于链接的第一部分大致相同：

- `[hobbit-hole][1]`
- `[hobbit-hole] [1]`

#### 格式化链接的第二部分

引用样式链接的第二部分使用以下属性设置格式：

1. 标签放在方括号中，后紧跟冒号和至少一个空格（例如 `[label]: `）。
2. 链接的URL，您可以选择将其括在尖括号中。
3. 链接的可选标题，您可以将其括在双引号，单引号或括号中。

这意味着以下示例格式对于链接的第二部分几乎都是等效的：

- `[1]: https://en.wikipedia.org/wiki/Hobbit#Lifestyle`
- `[1]: https://en.wikipedia.org/wiki/Hobbit#Lifestyle "Hobbit lifestyles"`
- `[1]: https://en.wikipedia.org/wiki/Hobbit#Lifestyle 'Hobbit lifestyles'`
- `[1]: https://en.wikipedia.org/wiki/Hobbit#Lifestyle (Hobbit lifestyles)`
- `[1]: <https://en.wikipedia.org/wiki/Hobbit#Lifestyle> "Hobbit lifestyles"`
- `[1]: <https://en.wikipedia.org/wiki/Hobbit#Lifestyle> 'Hobbit lifestyles'`
- `[1]: <https://en.wikipedia.org/wiki/Hobbit#Lifestyle> (Hobbit lifestyles)`

您可以将链接的第二部分放在Markdown文档中的任何位置。 有些人将它们放在出现的段落之后，而其他人则将它们放在文档的末尾（例如尾注或脚注）。

#### 将零件放在一起的示例

假设您添加一个URL作为 到段落 的 [标准URL链接](https://markdown.p2hp.com/basic-syntax/index.html#links) ，并且在Markdown中看起来像这样：

```
In a hole in the ground there lived a hobbit. Not a nasty, dirty, wet hole, filled with the ends
of worms and an oozy smell, nor yet a dry, bare, sandy hole with nothing in it to sit down on or to
eat: it was a [hobbit-hole](https://en.wikipedia.org/wiki/Hobbit#Lifestyle "Hobbit lifestyles"), and that means comfort.
```

尽管它可能指向有趣的附加信息，但显示的URL确实不会给现有的原始文本增加太多，除了使其难以阅读之外。 要解决此问题，您可以改为设置网址格式：

```
In a hole in the ground there lived a hobbit. Not a nasty, dirty, wet hole, filled with the ends
of worms and an oozy smell, nor yet a dry, bare, sandy hole with nothing in it to sit down on or to
eat: it was a [hobbit-hole][1], and that means comfort.

[1]: <https://en.wikipedia.org/wiki/Hobbit#Lifestyle> "Hobbit lifestyles"
```

在上述两种情况下，呈现的输出将相同：

> 在地上的一个洞里住着一个霍比特人。 这不是一个肮脏，肮脏，潮湿的洞，里面充满蠕虫的末端和难闻的气味，也没有一个干燥，裸露，沙质的洞，里面没有东西可以坐下或进食：那是一个 [霍比特洞](https://en.wikipedia.org/wiki/Hobbit#Lifestyle "霍比特人的生活方式") ，意味着舒适。

链接HTML为：

```
<a href="https://en.wikipedia.org/wiki/Hobbit#Lifestyle" title="Hobbit lifestyles">hobbit-hole</a>
```

## 图片

要添加图像，添加感叹号（`!`），然后在括号中 添加 替代文本，并在括号中添加图像资源的路径或URL。 您可以选择在括号中的URL之后添加标题。

```
![Philadelphia's Magic Gardens. This place was so cool!](/assets/images/philly-magic-gardens.jpg "Philadelphia's Magic Gardens")
```

呈现的输出如下所示：

![费城的魔法花园。 这个地方真酷！](https://d33wubrfki0l68.cloudfront.net/eab45e25bb79970178fab7a2d10cba0209372a59/94d9e/assets/images/philly-magic-garden.jpg "费城魔术花园")

### 链接图像

要向图像添加链接，将图像的Markdown括在方括号中，然后在括号中添加链接。

```
[![An old rock in the desert](/assets/images/shiprock.jpg "Shiprock, New Mexico by Beau Rogers")](https://www.flickr.com/photos/beaurogers/31833779864/in/photolist-Qv3rFw-34mt9F-a9Cmfy-5Ha3Zi-9msKdv-o3hgjr-hWpUte-4WMsJ1-KUQ8N-deshUb-vssBD-6CQci6-8AFCiD-zsJWT-nNfsgB-dPDwZJ-bn9JGn-5HtSXY-6CUhAL-a4UTXB-ugPum-KUPSo-fBLNm-6CUmpy-4WMsc9-8a7D3T-83KJev-6CQ2bK-nNusHJ-a78rQH-nw3NvT-7aq2qf-8wwBso-3nNceh-ugSKP-4mh4kh-bbeeqH-a7biME-q3PtTf-brFpgb-cg38zw-bXMZc-nJPELD-f58Lmo-bXMYG-bz8AAi-bxNtNT-bXMYi-bXMY6-bXMYv)
```

呈现的输出如下所示：

[![沙漠中的一块老石头](https://d33wubrfki0l68.cloudfront.net/70a143fdf134aacde3740662a2a47a2a1ee0d216/276c9/assets/images/shiprock.jpg "博罗杰斯（Beau Rogers），新墨西哥希普罗克（Shiprock）")](https://www.flickr.com/photos/beaurogers/31833779864/in/photolist-Qv3rFw-34mt9F-a9Cmfy-5Ha3Zi-9msKdv-o3hgjr-hWpUte-4WMsJ1-KUQ8N-deshUb-vssBD-6CQci6-8AFCiD-zsJWT-nNfsgB-dPDwZJ-bn9JGn-5HtSXY-6CUhAL-a4UTXB-ugPum-KUPSo-fBLNm-6CUmpy-4WMsc9-8a7D3T-83KJev-6CQ2bK-nNusHJ-a78rQH-nw3NvT-7aq2qf-8wwBso-3nNceh-ugSKP-4mh4kh-bbeeqH-a7biME-q3PtTf-brFpgb-cg38zw-bXMZc-nJPELD-f58Lmo-bXMYG-bz8AAi-bxNtNT-bXMYi-bXMY6-bXMYv)

## 转义字符

要显示原义字符，否则将用于设置Markdown文档中的文本格式 `\` ，在字符前面 添加反斜杠（ ）。

```
\* Without the backslash, this would be a bullet in an unordered list.
```

呈现的输出如下所示：

\*如果没有反斜杠，这将是无序列表中的项目符号。

### 你可以转义的字符

您可以使用反斜杠转义以下字符。

| 字符 | 名称 |
| --- | --- |
| \\ | 反斜杠 |
| \` | 刻度线（另参见 [转义刻度线中的代码](https://markdown.p2hp.com/basic-syntax/index.html#escaping-tick-marks) ） |
| \* | 星号 |
| \_ | 下划线 |
| {} | 大括号 |
| \[\] | 中括号 |
| () | 括号 |
| # | 井号 |
| + | 加号 |
| \- | 减号（连字符） |
| . | 点 |
| ! | 感叹号 |
| \| | 管道（另参见表中的 [转义管道](https://markdown.p2hp.com/extended-syntax/index.html#escaping-pipe-characters-in-tables) ） |

