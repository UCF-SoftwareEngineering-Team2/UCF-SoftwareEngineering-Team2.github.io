---
layout: page
title: Home 
tagline: homepage
---
{% include JB/setup %}

### Phase 1
<ul class="posts">
  {% for tag in site.tags.phase1 %}
      <li>
    		<a href="{{ BASE_PATH }}{{ tag.url }}">{{ tag.title }}</a>
      </li>
  {% endfor %}
</ul>

