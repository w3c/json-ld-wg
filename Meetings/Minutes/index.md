---
layout: default
---

# Meeting Minutes
{: .no_toc}

* TOC
{:toc}

## 2018

<ul>
{% for item in site.minutes reversed %}
  <li>{{ item.date | date: '%d %B' }}:
    <a href="{{ item.url }}">Telco Minutes</a>
  </li>
{% endfor %}
</ul>
