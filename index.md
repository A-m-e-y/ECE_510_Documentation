---
layout: base
---

# jekyll-timeline
## A timeline for your GitHub Pages that doesn't need plugins or JavaScript

Source, and readme on [GitHub](https://github.com/A-m-e-y/ECE_510_Documentation).

### Examples 
<ul class="timeline-examples">
  {% for post in site.posts %}
    <li class="post summary">
      <a href="{{ site.github.repository_url }}{{ post.url }}" title="{{ post.title }}">
        <!-- <p>{{ post.title }}</p> -->
        <img src="{{ site.github.repository_url }}/screencaps{{ post.id }}.png" />
      </a>
    </li>
  {% endfor %}
</ul>








