---
layout: post
category : Jekyll
title: Jekyll 블로그에 Google analytics 적용하기
date: 2016-12-11
tags: [jekyll, Google analytics]
---

> Google Analytics는 웹로그를 분석해주는 서비스로 웹페이지 방문자들의 사이트 활동, 사이트 유입경로 등의 자료를 제공한다. 이 기능은 간단하게 적용이 가능하다.

01.Google Analytics 계정 설정  

> [Google Analytics](https://analytics.google.com)에 계정을 생성하여 추적ID를 받는다.

**NOTE <i class="fa fa-exclamation-circle" aria-hidden="true"></i>** 추적ID와 추적 코드를 복사해두자!

![create google analytics](/img/posts/20161211/jekyll-with-google-analytics-01.png)


02._includes/google_analytics.html 생성  

> google_analytics.html를 생성하여 추적 코드를 붙여넣는다.

```
├── _includes
│   ├── google_analytics.html
```


03.google_analytics.html 스크립트 include

> _layouts/default.html 에 생성한 추적코드 스크립트 파일을 include한다.

{% highlight html %}
{%raw%}
// _layouts/default.html
...
  </head>
    {% include google_analytics.html %}
  <body>
  ...
  </body>
</html>
{%endraw%}
{% endhighlight %}

04._config.yml 파일 Google Analytics 에 대한 정보를 추가  

> YOUR_GOOGLE_ANALYTICS_ID에 추적 ID를 붙여넣는다.

{% highlight yml %}
//  _config.yml
...
# google analytics setting
google-analytics:
  id: "YOUR_GOOGLE_ANALYTICS_ID"

...  
{% endhighlight %}

05.실행 확인

> `jekyll build` 명령어 실행 이후 _site 에 index.html 상단 head에서 추적코드를 확인 할 수 있고, google analytics 보고 화면에서 방문자 세션으로 확인 할 수 있다.

![session check in google analytics](/img/posts/20161211/jekyll-with-google-analytics-02.png)

06.문제점

> 개발서버에서 실행 시 이 또한 분석에 추가되어 데이터 분석이 모호해진다.  
만약 `jekyll serve` 명령어로 서버를 실행시키는 경우 'localhost:4000'과 '172.0.0.1:4000'와 같은 운영체제에 의존하는 로컬 세션 또한 Google Analytics에 방문자로 인지하는 문제가 생긴다.

07.해결

> 위와 같은 문제를 해결하기 위해 개발서버에서 실행 하는 경우  [jekyll에 환경변수 값을 설정](http://jekyllrb-ko.github.io/docs/configuration/#jekyll--)하여 특정 환경에서만 사용되도록 한다. (자세한 환경변수 설정은 링크를 통해 확인 가능하다.)  
Jekyll 환경변수 디폴트 값은 development이므로 build의 전달인자 JEKYLL_ENV를 생략하면 아래와 같은 조건문을 통해 스크립트 로드가 실행되지 않게된다.

{% highlight html %}
{% raw %}
// _layouts/default.html
...
  {% if jekyll.environment == 'production' %}
  {% include google-analytics.html %}
  {% endif %}
  <body>
  ...
  </body>
</html>
{% endraw %}
{% endhighlight %}

**NOTE <i class="fa fa-exclamation-circle" aria-hidden="true"></i>** 개발환경에서 스크립트를 실행 시키고 싶다면?

```
$ JEKYLL_ENV=production jekyll build
```
