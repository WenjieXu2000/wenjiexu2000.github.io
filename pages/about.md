---
layout: page
title: About
description: Hello
keywords: Wenjie Xu, 徐文杰
comments: true
menu: 关于
permalink: /about/
---

Hello😎

## 联系

<ul>
{% for website in site.data.social %}
<li>{{website.sitename }}：<a href="{{ website.url }}" target="_blank">@{{ website.name }}</a></li>
{% endfor %}
{% if site.url contains 'wenjiexu2000.github.io' %}
<li>
<br />
<img style="height:192px;width:192px;border:1px solid lightgrey;" src="{{ site.url }}/assets/images/qrcode.png" alt="微信" />
</li>
{% endif %}
</ul>


## Keywords

{% for keyword in site.data.keywords %}
### {{ keyword.name }}
<div class="btn-inline">
{% for item in keyword.items %}
<button class="btn btn-outline" type="button">{{ item }}</button>
{% endfor %}
</div>
{% endfor %}
