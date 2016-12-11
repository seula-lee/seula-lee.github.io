---
layout: post
title:  Markdown cheatsheet
date: 2015-10-14
tags: [Markdown]
---

> 이 포스팅은  앞으로 모든 포스팅에서 사용될 Markdown에 대한 샘플로 <a href='http://assemble.io/docs/Cheatsheet-Markdown.html' target='_blank'>**Assemble**</a> 에서 작성된 Markdown cheatsheet 부분에 필요부분만 인용하여 작성하였다.

### 타이포그래피 (Typography)

#### 굵은 글씨 (Bold)

``` markdown
**rendered as bold text**
```
적용결과 :  **rendered as bold text**


#### 이탤릭체 (Italics)

``` markdown
_rendered as italicized text_
```

적용결과 :  _rendered as italicized text_


#### 표제 (Headings) : H1 ~ H6

``` markdown
# H1 Heading
## H2 Heading
### H3 Heading
#### H4 Heading
##### H5 Heading
###### H6 Heading
```
적용결과 :

# H1 Heading

## H2 Heading

### H3 Heading

#### H4 Heading

##### H5 Heading

###### H6 Heading


<div class="divider"></div>

### 각주 (Footnote)

각주를 표시하고 싶은 문장에 `[^1]` 로 작성하며 1~n 으로 순번 또는 영문으로 링크할 수 있고 클릭 시 해당 각주로 이동 가능하다.
각주는 쌍으로 존재하며
Example : footnote 1번 [^1]. footnote 2번 [^2] footnote a번 [^a]

<div class="divider"></div>

### 인용구 (Blockquote)
``` markdown
> Start by doing what's necessary; then do what's possible; and suddenly you are
doing the impossible. --Francis of Assisi
```

> Start by doing what's necessary; then do what's possible; and suddenly you are doing the impossible. --Francis of Assisi


<div class="divider"></div>

### 목록 항목 (List Items)

항목 표기는 **숫자**, *영문*, ***** , **- / +** 방식으로 이용할 수 있다.

**NOTE:** 연달아 사용하면

1. First order list item
1. Second item
a. third item ??
* Unordered list can use asterisks
- Or minuses
	+ Or pluses
	+ Or minuses


<div class="divider"></div>

### 코드 하이라이팅 (code Highlighting)
이 페이지는 <a href="http://pygments.org/">Pygments</a> 로 코드 하이라이팅을 제공하며 <a href="http://liquidmarkup.org/">Liquid tag</a> 를 이용하여 코드작성할 수 있다.
{% raw  %}
{% highlight javascript %}
var a = "hello world";
console.log("greeting to code : "+ a);
{% endhighlight %}
{% endraw %}


적용결과 :

{% highlight javascript %}
var a = "hello world";
console.log("greeting to code : "+ a);
{% endhighlight %}


### 코드 블록(Code Blocks)

```javascript
var s = "JavaScript syntax highlighting";
alert(s);
```
```
No language indicated, so no syntax highlighting.
But let's throw in a <b>tag</b>.
```

<b>tag</b>

<div class="divider"></div>

### 표 (Table)

#### Table 1: 정렬

```markdown
| left         | center        | right  |
| ------------ |:-------------:| ------:|
| col 1 is     | left-aligned  |  ---   |
| col 2 is     | centered      |  :---: |
| col 3 is     | right-aligned |  ---:  |
```
적용결과 :

| left         | center        | right  |
| ------------ |:-------------:| ------:|
| col 1 is     | left-aligned  |  ---   |
| col 2 is     | centered      |  :---: |
| col 3 is     | right-aligned |  ---:  |


#### Table 2: Typography 사용

```markdown
Markdown | Less | Pretty
--- | --- | ---
*Still* | `renders` | **nicely**
1 | 2 | 3
```
적용결과 :

Markdown | Less | Pretty
--- | --- | ---
*Still* | `renders` | **nicely**
1 | 2 | 3

<div class="divider"></div>

### 가로선 (Horizontal Line)

HTML 의 `<hr>` 을 Markdown 으로 다음과 같이 만들 수 있다.

* `___`: three consecutive underscores
* `---`: three consecutive dashes
* `***`: three consecutive asterisks

적용결과 :

___

---

***

<div class="divider"></div>

### 미디어

#### 동영상

<iframe width="560" height="315" src="https://www.youtube.com/embed/cKWzXaAeeQs" frameborder="0" allowfullscreen></iframe>

#### 이미지

![traveled to macau](/img/20150916_macau_1.jpg)


<div class="divider"></div>

### 각주 (Footnotes)

[^1]: Footnote 1 !!!

[^2]: Footnote 2 : 링크를 달수도 있다. - [click here!]({{ site.baseurl }}/about)

[^a]: Footnote a : 번호로 시작했기때문에 각주 a 이지만 3으로 표시된다.
