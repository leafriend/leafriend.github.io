---
layout: page
title: "Eclpse 설정"
---

Useful Templates
----------------------------------------

Window &rarr; Preferences &rarr; Java &rarr; Editor &rarr; Templates

*See [StackOverflow](http://stackoverflow.com/questions/1028858/useful-eclipse-java-code-templates) for more templates.*

### SLF4J

{% highlight java %}
${:import(org.slf4j.Logger,org.slf4j.LoggerFactory)}
private static final Logger LOGGER = LoggerFactory.getLogger(${enclosing_type}.class);
{% endhighlight %}

\- <http://stackoverflow.com/a/1029304/726439>
