---
title: Excerpts
---

# Excerpts

<ul class="post-list">
{% assign items = site.pages | where_exp: "p", "p.dir == '/excerpts/'" | where_exp: "p", "p.name != 'index.md'" | sort: "date" | reverse %}
{% for p in items %}
  <li>
    <a href="{{ p.url | relative_url }}">{{ p.title | default: p.name }}</a>
    <span class="meta">{% if p.date %}{{ p.date | date: "%B %-d, %Y" }}{% endif %}{% if p.status and p.status != "finished" %} · {{ p.status }}{% endif %}</span>
  </li>
{% endfor %}
</ul>
