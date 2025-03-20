---
layout: default
title: Tags
---

# Tags
<ul>
    {% assign tags = site.tags | sort %}
    {% for tag in tags %}
        <a class="post-tags" href="/tags.html#{{ tag[0] }}">#{{ tag[0] }}</a>
    {% endfor %}
</ul>

# Posts by tag
{% for tag in tags %}
{% assign tag_name = tag | first %}
## #{{ tag_name }}
<ul>
    {% for post in site.tags[tag_name] %}
    <li>
        {%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
        <b>
            <a href="{{ post.url | relative_url }}">
                {{ post.title | escape }}
            </a>
        </b> - <i>{{ post.date | date: date_format }}</i>
    </li>
    {% endfor %}
</ul>
{% endfor %}

