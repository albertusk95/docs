---
layout: base
title:  'Features'
generated: 'true'
permalink: hy/feat/all.html
---

# Features

{% include hy-feat-table.html %}

----------

{% assign sorted = site.hy-feat | sort: 'title' %}{% for p in sorted %}
<a id="al-hy-feat/{{ p.title }}" class="al-dest"/>
<h2><code>{{ p.title }}</code>: {{ p.shortdef }}</h2>
{% if p.content contains "<!--details-->" %}    
{{ p.content | split:"<!--details-->" | first }}
<a href="{{ p.title }}" class="al-doc">See details</a>
{% else %}
{{ p.content }}
{% endif %}
<a href="{{ site.git_edit }}/{% if p.collection %}{{ p.relative_path }}{% else %}{{ p.path }}{% endif %}" target="#">edit {{ p.title }}</a>
{% endfor %}
