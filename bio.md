---
layout: page
title: Bio
permalink: /bio/
---

{% assign bio_sections = site.bio | sort: 'order' %}
{% for section in bio_sections %}
## {{ section.title }}

{{ section.content | markdownify }}
{% endfor %}
