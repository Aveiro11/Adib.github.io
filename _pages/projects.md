---
layout: archive
title: "Projects"
permalink: /projects/
author_profile: true
---

{% if site.author.github %}
  <div class="wordwrap">You can also find my other projects on <a href="{{site.author.github}}">my Github profile</a>.</div>
{% endif %}

{% include base_path %}

{% for post in site.projects reversed %}
  {% include archive-single.html %}
{% endfor %}
