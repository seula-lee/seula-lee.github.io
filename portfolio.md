---
layout: page
title: portfolio
permalink: /portfolio/
---
<div id="projects">
{% for project in site.portfolio %}
    <div class="pr-col-1 pr-col-2">
      <div class="pr-ex site-box">
          <a href="{{ site.baseurl }}{{ project.url }}">
          <div class="pr-ex-img">
            {% if project.img %}
            <img src="{{ project.img }}"/>
            {% endif %}    
          </div>
          <div class="pr-ex-desc">
            <span class="pr-ex-name">{{ project.title }}</span>
            <span class="pr-ex-year">{{ project.year }}</span>
          </div>  
          </a>
      </div>
    </div>
{% endfor %}
</div>
