---
layout: post
title: "GitHub Pages와 Jekyll 로컬 전용 설정"
date: 2015-06-15 11:06:24
categories: dev
tags:
  - GitHub Pages
  - Jekyll
---

GitHub Pages와 Jekyll을 사용할 때 로컬에서는 별도의 설정을 적용하고 싶을 때가 있습니다. 다음은 구글 애널리틱스 추적 ID를 로컬에서 삽입하지 않게 하는 예제입니다.

설정 파일
----------------------------------------

먼저 기본 설정 파일인 `_cofnig.yml` 파일에 구글 애널리틱스 코드를 추가합니다.

{% highlight yaml %}
google_analytics_tracking_id: "UA-000000-01"
{% endhighlight %}

그리고 로컬에서만 사용할 `_cofnig-local.yml` 설정 파일에서 구글 애널리틱스 코드를 다시 정의합니다.

{% highlight yaml %}
google_analytics_tracking_id: ""
{% endhighlight %}

이렇게 추가한 로컬 설정 파일은 GitHub로 전송하지 않도록 `.gitignore`에 위 파일을 추가합니다.

    _cofnig-local.yml

구글 애널리틱스 추적 코드/ID 삽입
----------------------------------------

설정 파일을 준비한 다음 구글 애널리틱스 추적 코드/ID를 추가합니다. `_layouts/default.html` 파일이나 원하는 곳에 아래와 같이 추가합니다.

{% highlight liquid %}
{% raw %}
{% if site.google_analytics_tracking_id and site.google_analytics_tracking_id != '' %}
<script>
  (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
  (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
  m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
  })(window,document,'script','//www.google-analytics.com/analytics.js','ga');

  ga('create', '{{ google_analytics_tracking_id }}', 'auto');
  ga('send', 'pageview');
</script>
{% endif %}
{% endraw %}
{% endhighlight %}

[구글에서 제공하는 추적 코드](https://support.google.com/analytics/answer/1032385?hl=ko)에서 추적 ID 부분만 설정 파일에서 지정한 값으로 바꾸면 됩니다.

로컬에서 실행
----------------------------------------

위와 같이 설정한 다음 로컬에서 Jeykyll을 실행할 때 기본 설정 파일에 로컬 설정 파일(`_config-local.yml`)을 추가로 지정하여 실행하면 됩니다.

    jekyll serve --config _config.yml,_config-local.yml

실행할 때 기본 설정 파일(`_config.yml`)을 빠뜨리고 실행하면 오류는 발생하지 않지만 모든 설정이 기본값으로 적용되기 때문에 주의해야 합니다.
