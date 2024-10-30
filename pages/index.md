---
layout: default
title: Home
permalink: /
---
# Home

{::nomarkdown}
    {% for item in site.data.navigation %}
        {% if item.link != page.url %}
            <a class="nav-link" href="{{ item.link }}">{{ item.name }}</a>
        {% endif %}
    {% endfor %}
{:/}