---
layout: post
title: Markdown基本语法
category: 技术
tags: Markdown
keywords: Markdown
description: Markdown basic syntax
---


## 标题

使用 `#` 符号创建标题，符号的数量应对应标题级别。例如，要创建三级标题（`<h3>`），请使用三个 `#`，如 `### My Header`。

| Markdown                 | HTML                        | 渲染输出         |
| ------------------------ | --------------------------- | ------------ |
| `# Heading level 1`      | `<h1>Heading level 1</h1>`  | # 标题等级1      |
| `## Heading level 2`     | `<h2>Heading level 2</h2>`  | ## 标题等级2     |
| `### Heading level 3`    | `<h3>Heading level 3</h3>`  | ### 标题级别3    |
| `#### Heading level 4`   | `<h4>Heading level 4</h4>`  | #### 标题级别4   |
| `##### Heading level 5`  | `<h5>Heading level 5</h5>`  | ##### 标题5      |
| `###### Heading level 6` | `<h6>Heading level 6</h6>`  | ###### 标题等级6 |

### 替代语法

也可以在文本下方添加一行由 `=`（表示一级标题）或 `-`（表示二级标题）组成的字符。

| Markdown           | HTML                    | 渲染输出     |
| ------------------ | ----------------------- | ------------ |
| `Heading level 1`   | `<h1>Heading level 1</h1>` | # 标题等级1  |
| `Heading level 2`   | `<h2>Heading level 2</h2>` | ## 标题等级2 |

## 段落

段落由一行或多行文本组成，使用空行分隔。段落不应缩进空格或制表符。

| Markdown                                         | HTML                                              | 渲染输出                       |
| ------------------------------------------------| -------------------------------------------------| ------------------------------|
| `I really like using Markdown.`<br>`I think I'll use it to format all of my documents from now on.` | `<p>I really like using Markdown.</p>`<br>`<p>I think I'll use it to format all of my documents from now on.</p>` | 我真的很喜欢使用Markdown。<br>我想从现在开始用它格式化所有文档。 |

## 换行

在一行末尾添加两个或多个空格后按回车，可以创建换行符（`<br>`）。

| Markdown                                    | HTML                                  | 渲染输出        |
| -------------------------------------------| ------------------------------------| --------------- |
| `This is the first line.  ` <br> `And this is the second line.` | `<p>This is the first line.<br>And this is the second line.</p>` | 这是第一行。<br>这是第二行。 |

## 着重

可通过加粗或斜体来突出文本。

### 粗体

在单词或短语前后添加两个星号或下划线，实现加粗。加粗单词中间部分时，两侧星号紧贴字母，无空格。

| Markdown           | HTML                       | 渲染输出          |
| ------------------ | -------------------------- | ----------------- |
| `I just love **bold text**.` | `I just love <strong>bold text</strong>.` | 我只喜欢 **粗体字**。 |
| `I just love __bold text__.` | `I just love <strong>bold text</strong>.` | 我只喜欢 **粗体字**。 |
| `Love**is**bold`      | `Love<strong>is</strong>bold`   | 爱 **是**大胆的    |

### 斜体

在单词或短语前后添加一个星号或下划线，实现斜体。斜体单词中间部分时，星号紧贴字母，无空格。

| Markdown                | HTML                            | 渲染输出         |
| ----------------------- | -------------------------------| ---------------- |
| `Italicized text is the *cat's meow*.` | `Italicized text is the <em>cat's meow</em>.` | 斜体文字是 *猫的叫声*。 |
| `Italicized text is the _cat's meow_.` | `Italicized text is the <em>cat's meow</em>.` | 斜体文字是 *猫的叫声*。 |
| `A*cat*meow`             | `A<em>cat</em>meow`             | 一个 *猫* 喵       |

### 粗体和斜体

在单词或短语前后添加三个星号或下划线，可同时加粗和斜体。

| Markdown                         | HTML                                      | 渲染输出          |
| --------------------------------| ----------------------------------------- | ----------------- |
| `This text is ***really important***.` | `This text is <strong><em>really important</em></strong>.` | 这段文字 ***真的很重要***。|
| `This text is ___really important___.` | `This text is <strong><em>really important</em></strong>.` | 这段文字 ***真的很重要***。|
| `This text is __*really important*__.` | `This text is <strong><em>really important</em></strong>.` | 这段文字 ***真的很重要***。|
| `This text is **_really important_**.` | `This text is <strong><em>really important</em></strong>.` | 这段文字 ***真的很重要***。|

## 块引用

在段落前添加 `>` 创建块引用。

```
> Dorothy followed her through many of the beautiful rooms in her castle.
```

渲染输出：

> Dorothy followed her through many of the beautiful rooms in her castle.

### 多段块引用

多个段落块引用间用带 `>` 的空白行分隔。

```
> Dorothy followed her through many of the beautiful rooms in her castle.
>
> The Witch bade her clean the pots and kettles and sweep the floor and keep the fire fed with wood.
```

渲染输出：

> Dorothy followed her through many of the beautiful rooms in her castle.
>
> The Witch bade her clean the pots and kettles and sweep the floor and keep the fire fed with wood.

### 嵌套块引用

在段落前加多个 `>` 形成嵌套块引用。

```
> Dorothy followed her through many of the beautiful rooms in her castle.
>
>> The Witch bade her clean the pots and kettles and sweep the floor and keep the fire fed with wood.
```

渲染输出：

> Dorothy followed her through many of the beautiful rooms in her castle.
>
>> The Witch bade her clean the pots and kettles and sweep the floor and keep the fire fed with wood.

### 含其他元素的块引用

块引用能包含其他Markdown元素。具体支持元素需自行测试。

```
> #### The quarterly results look great!
>
> - Revenue was off the chart.
> - Profits were higher than ever.
>
>  *Everything* is going according to **plan**.
```

渲染输出：

> #### The quarterly results look great!
>
> - Revenue was off the chart.
> - Profits were higher than ever.
>
> *Everything* is going according to **plan**.

## 清单

项目可组织成有序或无序列表。

### 有序列表

在项目前加数字和句点创建有序列表。数字可不连续，列表应以数字开头。

| Markdown                                     | HTML                                  | 渲染输出               |
|----------------------------------------------|-------------------------------------|------------------------|
| `1. First item`<br>`2. Second item`          | `<ol><li>First item</li><li>Second item</li></ol>` | 1. 第一项<br>2. 第二项   |
| `1. First item`<br>`1. Second item`          | `<ol><li>First item</li><li>Second item</li></ol>` | 1. 第一项<br>2. 第二项   |
| `1. First item`<br>`8. Second item`          | `<ol><li>First item</li><li>Second item</li></ol>` | 1. 第一项<br>2. 第二项   |
| `1. First item`<br>`2. Second item`<br>&nbsp;&nbsp;&nbsp;&nbsp;`1. Indented item`<br>&nbsp;&nbsp;&nbsp;&nbsp;`2. Indented item`<br>`4. Fourth item` | `<ol><li>First item</li><li>Second item<ol><li>Indented item</li><li>Indented item</li></ol></li><li>Fourth item</li></ol>` | 1. 第一项<br>2. 第二项<br>&nbsp;&nbsp;&nbsp;&nbsp;1. 缩进项<br>&nbsp;&nbsp;&nbsp;&nbsp;2. 缩进项<br>4. 第四项 |

### 无序列表

在项目前添加破折号（`-`）、星号（`*`）或加号（`+`）创建无序列表缩进项目以创建嵌套。

| Markdown                                                                                                                                       | HTML                                                                                                                        | 渲染输出                                                                                      |
| ---------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| `- First item`<br>`- Second item`                                                                                                              | `<ul><li>First item</li><li>Second item</li></ul>`                                                                          | - 第一项<br>- 第二项                                                                            |
| `* First item`<br>`* Second item`                                                                                                              | `<ul><li>First item</li><li>Second item</li></ul>`                                                                          | - 第一项<br>- 第二项                                                                            |
| `+ First item`<br>`* Second item`<br>`- Third item`<br>`+ Fourth item`                                                                         | `<ul><li>First item</li><li>Second item</li><li>Third item</li><li>Fourth item</li></ul>`                                   | - 第一项<br>- 第二项<br>- 第三项<br>- 第四项                                                          |
| `- First item`<br>`- Second item`<br>&nbsp;&nbsp;&nbsp;&nbsp;`- Indented item`<br>&nbsp;&nbsp;&nbsp;&nbsp;`- Indented item`<br>`- Fourth item` | `<ul><li>First item</li><li>Second item<ul><li>Indented item</li><li>Indented item</li></ul></li><li>Fourth item</li></ul>` | - 第一项<br>- 第二项<br>&nbsp;&nbsp;&nbsp;&nbsp;- 缩进项<br>&nbsp;&nbsp;&nbsp;&nbsp;- 缩进项<br>- 第四项 |

### 列表中添加新元素

在列表项下添加元素时，缩进四个空格或一个制表符以保持列表连续。

#### 段落示例

```
* This is the first list item.
* Here's the second list item.

    I need to add another paragraph below the second list item.

* And here's the third list item.
```

渲染输出：

* This is the first list item.
* Here's the second list item.

    I need to add another paragraph below the second list item.

* And here's the third list item.

#### 块引用示例

```
* This is the first list item.
* Here's the second list item.

    > A blockquote would look great below the second list item.

* And here's the third list item.
```

渲染输出：

* This is the first list item.
* Here's the second list item.

    > A blockquote would look great below the second list item.

* And here's the third list item.

#### 代码块示例

代码块通常缩进四个空格或一个制表符，在列表中需缩进八个空格或两个制表符。

```
1. Open the file.
2. Find the following code block on line 21:

        <html>
          <head>
            <title>Test</title>
          </head>

3. Update the title to match the name of your website.
```

渲染输出：

1. Open the file.
2. Find the following code block on line 21:

        <html>
          <head>
            <title>Test</title>
          </head>

3. Update the title to match the name of your website.

#### 图片示例

```
1. Open the file containing the Linux mascot.
2. Marvel at its beauty.

    ![Tux, the Linux mascot](/assets/images/tux.png)

3. Close the file.
```

渲染输出：

1. Open the file containing the Linux mascot.
2. Marvel at its beauty.
    ![Tux，Linux吉祥物](https://d33wubrfki0l68.cloudfront.net/e7ed9fe4bafe46e275c807d63591f85f9ab246ba/e2d28/assets/images/tux.png)
3. Close the file.

## 代码

使用反引号（`` ` ``）将单词或短语标记为代码。

| Markdown               | HTML                        | 渲染输出       |
| ---------------------- | ---------------------------| -------------- |
| ``At the command prompt, type `nano`.`` | `At the command prompt, type <code>nano</code>.` | 在命令提示符下，键入 `nano`。 |

### 转义反引号

要表示包含反引号的代码片段，用双反引号（````）包裹。

| Markdown                      | HTML                                    | 渲染输出                 |
| -----------------------------| ---------------------------------------| ------------------------ |
| ``` ``Use `code` in your Markdown file.`` ``` | `<code>Use `code` in your Markdown file.</code>` | ``Use `code` in your Markdown file.`` |

### 代码块

创建代码块时，每行缩进至少四个空格或一个制表符。

```
<html>
  <head>
  </head>
</html>
```

渲染输出：

```
<html>
  <head>
  </head>
</html>
```

## 水平线

水平线由独立一行的三个或更多星号（`***`）、破折号（`---`）或下划线（`___`）组成。

```
***

---

___
```

渲染输出相同：

***

---

___

## 链接

将链接文本放在方括号中，紧接着在圆括号中添加URL。

```
My favorite search engine is [Duck Duck Go](https://duckduckgo.com).
```

渲染输出：

My favorite search engine is [Duck Duck Go](https://duckduckgo.com).

### 添加标题

在URL后加上包含标题的引号，悬浮显示工具提示。

渲染输出：

我最喜欢的搜索引擎是 [Duck Duck Go](https://duckduckgo.com/ "最好的隐私搜索引擎")。

### URL和电子邮件地址

用尖括号包围URL或邮箱，可快速转换为链接。

```
<https://markdown.p2hp.com>
<fake@example.com>
```

渲染输出：

[https://markdown.p2hp.com](https://markdown.p2hp.com/index.html)  
[fake@example.com](mailto:fake@example.com)

### 格式化链接

可用星号为链接加粗或斜体，格式在方括号和括号之前和之后添加。

```
I love supporting the **[EFF](https://eff.org)**.
This is the *[Markdown Guide](https://markdown.p2hp.com)*.
```

渲染输出：

I love supporting the **[EFF](https://eff.org)**.  
This is the *[Markdown Guide](https://markdown.p2hp.com)*.

### 参考样式链接

参考样式链接将URL与链接文本分开，便于阅读。

#### 第一部分格式

使用两组括号，第一组方括号为链接文本，第二组括号为标签。

示例：

- `[hobbit-hole][1]`  
- `[hobbit-hole] [1]`

#### 第二部分格式

定义标签与URL映射：

- 标签用方括号包裹，后跟冒号和空格  
- URL可加尖括号  
- 可选标题用引号或括号包裹

示例：

- `[1]: https://en.wikipedia.org/wiki/Hobbit#Lifestyle "Hobbit lifestyles"`

位置不限制，可放在文档任何处。

#### 示例组合

```
In a hole in the ground there lived a hobbit. Not a nasty, dirty, wet hole, filled with the ends
of worms and an oozy smell, nor yet a dry, bare, sandy hole with nothing in it to sit down on or to
eat: it was a [hobbit-hole][1], and that means comfort.

[1]: https://en.wikipedia.org/wiki/Hobbit#Lifestyle "Hobbit lifestyles"
```

渲染输出：

In a hole in the ground there lived a hobbit. Not a nasty, dirty, wet hole, filled with the ends
of worms and an oozy smell, nor yet a dry, bare, sandy hole with nothing in it to sit down on or to
eat: it was a [hobbit-hole][1], and that means comfort.

[1]: https://en.wikipedia.org/wiki/Hobbit#Lifestyle "Hobbit lifestyles"

对应HTML：

```html
<a href="https://en.wikipedia.org/wiki/Hobbit#Lifestyle" title="Hobbit lifestyles">hobbit-hole</a>
```

## 图片

添加感叹号，紧接方括号内的替代文本，后跟圆括号内的路径或URL，可选标题。

```
![Philadelphia's Magic Gardens. This place was so cool!](/assets/images/philly-magic-gardens.jpg "Philadelphia's Magic Gardens")
```

渲染输出：

![费城的魔法花园。 这个地方真酷！](https://d33wubrfki0l68.cloudfront.net/eab45e25bb79970178fab7a2d10cba0209372a59/94d9e/assets/images/philly-magic-garden.jpg "费城魔术花园")

### 带链接的图片

将图片的Markdown放入方括号，再紧跟链接。

```
[![An old rock in the desert](/assets/images/shiprock.jpg "Shiprock, New Mexico by Beau Rogers")](https://www.flickr.com/photos/beaurogers/31833779864/in/photolist-Qv3rFw-34mt9F-a9Cmfy-5Ha3Zi-9msKdv-o3hgjr-hWpUte-4WMsJ1-KUQ8N-deshUb-vssBD-6CQci6-8AFCiD-zsJWT-nNfsgB-dPDwZJ-bn9JGn-5HtSXY-6CUhAL-a4UTXB-ugPum-KUPSo-fBLNm-6CUmpy-4WMsc9-8a7D3T-83KJev-6CQ2bK-nNusHJ-a78rQH-nw3NvT-7aq2qf-8wwBso-3nNceh-ugSKP-4mh4kh-bbeeqH-a7biME-q3PtTf-brFpgb-cg38zw-bXMZc-nJPELD-f58Lmo-bXMYG-bz8AAi-bxNtNT-bXMYi-bXMY6-bXMYv)
```

渲染输出：

[![沙漠中的一块老石头](https://d33wubrfki0l68.cloudfront.net/70a143fdf134aacde3740662a2a47a2a1ee0d216/276c9/assets/images/shiprock.jpg "博罗杰斯（Beau Rogers），新墨西哥希普罗克（Shiprock）")](https://www.flickr.com/photos/beaurogers/31833779864/in/photolist-Qv3rFw-34mt9F-a9Cmfy-5Ha3Zi-9msKdv-o3hgjr-hWpUte-4WMsJ1-KUQ8N-deshUb-vssBD-6CQci6-8AFCiD-zsJWT-nNfsgB-dPDwZJ-bn9JGn-5HtSXY-6CUhAL-a4UTXB-ugPum-KUPSo-fBLNm-6CUmpy-4WMsc9-8a7D3T-83KJev-6CQ2bK-nNusHJ-a78rQH-nw3NvT-7aq2qf-8wwBso-3nNceh-ugSKP-4mh4kh-bbeeqH-a7biME-q3PtTf-brFpgb-cg38zw-bXMZc-nJPELD-f58Lmo-bXMYG-bz8AAi-bxNtNT-bXMYi-bXMY6-bXMYv)

## 转义字符

用反斜杠（`\`）转义将被识别为Markdown符号的字符，以显示其原义。

```
\* Without the backslash, this would be a bullet in an unordered list.
```

渲染输出：

\* Without the backslash, this would be a bullet in an unordered list.

### 可转义字符列表

可转义字符包括：

| 字符 | 名称 |
| --- | --- |
| \\ | 反斜杠 |
| \` | 反引号 |
| \* | 星号 |
| \_ | 下划线 |
| {} | 大括号 |
| \[\] | 中括号 |
| () | 括号 |
| # | 井号 |
| + | 加号 |
| \- | 减号（连字符） |
| . | 句点 |
| ! | 感叹号 |
| \| | 竖线 |

