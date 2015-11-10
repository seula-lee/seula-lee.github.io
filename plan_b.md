---
layout: page
permalink: /plan_b/
title: plan B
description: Planing and performing
---

<ul class="post-list">
{% for poem in site.plan_b reversed %}
    <li>
        <h2><a class="poem-title" href="{{ poem.url | prepend: site.baseurl }}">{{ poem.title }}</a></h2>
        <p class="post-meta">{{ poem.date | date: '%B %-d, %Y — %H:%M' }}</p>
      </li>
{% endfor %}
</ul>