---
layout: post
category : Jekyll
title:  Jekyll 태그 추가하기
date: 2016-12-04
tags: [jekyll, Liquid, tag]
---
출처 > <a href="http://kalapun.com/posts/liquid-tag-management-for-jekyll/" target="_blank"> Liquid tag management for Jekyll</a>

> Jekyll은 블로깅하기에 단순 명료하나, 플러그인에 제한적이라는 단점이 있다.
카테고리별로 분리해서 글을 보기위해 Jekyll에 태그기능을 적용하고 싶어 Jekyll-tagging 이라는 플러그인을 사용하려다 Jekyll version에 따라서 정상 동작하지 않는 다는 것을 확인하고 위 출처의 블로그를 참고하여 <a href="https://github.com/Shopify/liquid/wiki/Liquid-for-Designers" target="_blank">Liquid</a>에서 제공하는 tags 기능을 적용해 보았다.

#### tag.html 생성
> 태그 리스트와 각 태그에 해당하는 게시글을 모아 볼 수 있는 화면을 생성한다.

{% highlight html %}
{% raw %}
---
layout: page
title: Tags
permalink: /tags/
---
<ul class="tag-cloud">
{% for tag in site.tags %}
  <li style="font-size: {{ tag | last | size | times: 100 | divided_by: site.tags.size | plus: 70  }}%">
    <a href="#{{ tag | first | slugize }}">
        {{ tag | first }}
    </a>
  </li>
{% endfor %}
</ul>

<div id="blog-archives">
{% for tag in site.tags %}
  {% capture tag_name %}{{ tag | first }}{% endcapture %}
  <h3 id="#{{ tag_name | slugize }}">{{ tag_name }}</h3>
  <a name="{{ tag_name | slugize }}"></a>
  {% for post in site.tags[tag_name] %}
  <article>
    <h3><a href="{{ root_url }}{{ post.url }}">{{post.title}}</a></h3>
  </article>
  {% endfor %}
{% endfor %}
</div>
{% endraw %}
{% endhighlight %}

#### 스타일 적용
> main.css에 스타일을 추가한다.
{% highlight scss %}
.tag-cloud {
  list-style: none;
  padding: 0;
  margin: 0 !important;
  text-align: justify;
  font-size: 0.8em;
  li {
    background-color: #888;
    display: inline-block;
    padding: 0.2em 1em;
  }
  li a{
    color: #fff;
  }
}
#archives {
  padding: 5px;
}
.archive-group {
  margin: 5px;
  border-top: 1px solid #ddd;
}
.archive-item {
  margin-left: 5px;
}
.post-tags {
  padding: 7.5px 0;
}
.post-tag-pill{
  padding: 0.2em 1em;
  color: #fff;
  background-color: #888;
  font-size: 0.8em;
}
{% endhighlight %}

#### 포스트에 태그 표시
> _includes/post-tags.html 생성한다.

{% highlight html%}
{% raw %}
<div class="post-tags">
  Tags:
  {% if post %}
    {% assign tags = post.tags %}
  {% else %}
    {% assign tags = page.tags %}
  {% endif %}
  {% for tag in tags %}
  <a href="/tags/#{{tag|slugize}}">{{tag}}</a>{% unless forloop.last %},{% endunless %}
  {% endfor %}
</div>
{% endraw %}
{% endhighlight %}

> post.html에 생성한 post_tags.html 파일을 include한다. 
{% highlight html %}
{% raw %}
{% include post_tags.html %}
{% endraw %}
{% endhighlight %}
