---
layout: default
title: Index
permalink: /
---

{::nomarkdown}
    {% for item in site.data.navigation %}
        {% if item.link != page.url %}
            <a class="nav-link px-0 h3" href="{{ item.link }}">{{ item.name }}</a>
        {% endif %}
    {% endfor %}
{:/}