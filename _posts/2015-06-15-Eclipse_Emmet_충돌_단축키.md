---
layout: post
title: "Eclipse Emmet 충돌 단축키"
date: 2015-06-15 02:47:04
categories: dev
tags:
  - Eclipse
  - Emmet
  - Zen Coding
---

[Emmet](http://emmet.io/)은 Zen Coding으로도 알려진 도구로 다음과 같은 입력을 HTML로 바꿔준다.

입력:

    div#page>div.logo+ul#navigation>li*5>a

출력:

{% highlight html %}
<div id="page">
        <div class="logo"></div>
        <ul id="navigation">
                <li><a href=""></a></li>
                <li><a href=""></a></li>
                <li><a href=""></a></li>
                <li><a href=""></a></li>
                <li><a href=""></a></li>
        </ul>
</div>
{% endhighlight %}

[이클립스 플러그인](https://github.com/emmetio/emmet-eclipse)도 있는데 사용하다 보면 자주 사용하는 기존 단축키와 충돌하는 Emmet 단축키가 많아 불편하다. 다음은 플러그인에서 기본으로 설정된 단축키와 충돌하는 단축키다. 단축키가 없는 명령은 제외했다.

Emmet Command           | Binding                                       | Conflict Command / When / Category
----------------------- | --------------------------------------------- | -------------
Encode/Decode Data:URL  | <kbd>Alt</kbd>+<kbd>Shift</kbd>+<kbd>I</kbd>  | Inline / In Windows / Refactor - Java<br>Inline JavaScript View / Refactor - JavaScript<br>Mark Task Incompleted / In Tasks Editor / Task Repositories<br>Mark Task Incompleted / In Tasks View / Task Repositories
Expand Abbreviation     | <kbd>Ctrl</kbd>+<kbd>E</kbd>                  | Quick Switch Editor / In Windows / Window
Match Pair Inward       | <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd> | Add Maven Dependency / Editing XML Source / Edit<br>Display / In Dialog and Windows / Run/Debug
Match Pair Outward      | <kbd>Ctrl</kbd>+<kbd>D</kbd>                  | Delete Line / Editing Text / Text Editing
Merge LInes             | <kbd>Ctrl</kbd>+<kbd>M</kbd>                  | Maximize Active View or Eidor / In Windows / Window
Next Edit Point         | <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>]</kbd>   |
Previous Edit Point     | <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>[</kbd>   |
Remove Tag              | <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>I</kbd> | Inspect / In Dialog and Windows / Run/Debug
Split/Join Tag          | <kbd>Ctrl</kbd>+<kbd>U</kbd>                  | Execute / In Windows / Run/Debug
Toggle Comment          | <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>/</kbd> | Add Block Comment / Editing in Structured Text Editors / Edit<br>Add Block Comment / Editing Java Source / Source<br>Add Block Comment / Editing JavaScript Source / Source
Update Image Size       | <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>U</kbd> | Show Occurences in File Quick Menu / In Window / Search<br>Show Occurences in File Quick Menu / JavaScript View / Search
Wrap With Abbreviation  | <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>A</kbd> | Occurrences in File / Editing in Structured Text Editors / Edit<br>Open Plug-in Artifact / In Windows / Navigate

이 중에서 Expand Abbreviation (<kbd>Ctrl</kbd>+<kbd>E</kbd>) 명령이나 Match Pair Outward (<kbd>Ctrl</kbd>+<kbd>D</kbd>) 명령, Merge LInes (<kbd>Ctrl</kbd>+<kbd>M</kbd>) 명령 등은 자주 사용하는 명령어들(빠른 편집기 탐색, 현재 줄 삭제, 현재 편집기/뷰 최대화 토글)과 충돌이 일어나서 삭제하거나 바인딩을 바꾸는 게 좋다.