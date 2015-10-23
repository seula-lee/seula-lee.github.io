---
layout: post
title:  Markdown cheatsheet
date: 2015-10-14 
---

> 이 포스팅은  앞으로 모든 포스팅에서 사용될 Markdown에 대한 샘플로 <a href='http://assemble.io/docs/Cheatsheet-Markdown.html' target='_blank'>**Assemble**</a> 에서 작성된 markdown cheatsheet를 인용하고 있습니다.

## 문장 스타일 강조

### 굵은 글씨 (Bold)

``` markdown
**rendered as bold text**
```
renders to:

**rendered as bold text**

and this HTML

``` html
<strong>rendered as bold text</strong>
```

### Italics
For emphasizing a snippet of text with italics.

The following snippet of text is _rendered as italicized text_.

``` markdown
_rendered as italicized text_
```

renders to:

_rendered as italicized text_

and this HTML:

``` html
<em>rendered as italicized text</em>
```


### strikethrough
In GFM you can do strickthroughs. 

``` markdown
~~Strike through this text.~~
```
Which renders to:

~~Strike through this text.~~

<div class="divider"></div>

## Typography

## Headings H1 to H6

# H1 Heading

## H2 Heading

### H3 Heading

#### H4 Heading

##### H5 Heading

###### H6 Heading

<div class="divider"></div>

## Footnote

Let's say you have text that you want to refer with a footnote, you can do that too! This is an example for the footnote number one [^1]. You can even add more footnotes, with link! [^2]

<div class="divider"></div>

## Blockquote

> Start by doing what's necessary; then do what's possible; and suddenly you are doing the impossible. --Francis of Assisi

**NOTE:** This theme does NOT support nested blockquotes.

<div class="divider"></div>

## List Items

1. First order list item
2. Second item

* Unordered list can use asterisks
- Or minuses
+ Or pluses

<div class="divider"></div>

## Code Highlighting
This theme implements Jekyll's built in code syntax highlighting with Pygments. Just use a liquid tag to delineate your code: 
{% highlight python %}
	code code code
{% endhighlight %}

## Code Blocks

```javascript
var s = "JavaScript syntax highlighting";
alert(s);
```

```python
s = "Python syntax highlighting"
print s
```

```
No language indicated, so no syntax highlighting.
But let's throw in a <b>tag</b>.
```

<div class="divider"></div>

## Table

### Table 1: With Alignment

| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |

### Table 2: With Typography Elements

Markdown | Less | Pretty
--- | --- | ---
*Still* | `renders` | **nicely**
1 | 2 | 3

<div class="divider"></div>

## Horizontal Line

The HTML `<hr>` element is for creating a "thematic break" between paragraph-level elements. In markdown, you can create a `<hr>` with any of the following:

* `___`: three consecutive underscores
* `---`: three consecutive dashes
* `***`: three consecutive asterisks

renders to:

___

---

***

<div class="divider"></div>

## Media

### YouTube Embedded Iframe

<iframe width="560" height="315" src="https://www.youtube.com/embed/n1a7o44WxNo" frameborder="0" allowfullscreen></iframe>

### Image

![Minion](http://octodex.github.com/images/minion.png)

[^1]: Footnote number one yeah baby!

[^2]: A footnote you can link to - [click here!](#)
