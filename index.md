---
layout: base
---

# ECE 510 Documentation
## A timeline journal for Project and Weekly Challenges

Source, and readme on [GitHub](https://github.com/A-m-e-y/ECE_510_Documentation).

### Examples 

<ul class="timeline-examples">
  {% for post in site.posts %}
    <li class="post summary">
      <a href="{{ site.baseurl }}{{ post.url }}" title="{{ post.title }}">
        <!-- <p>{{ post.title }}</p> -->
        <img src="{{ site.baseurl }}/screencaps{{ post.id }}.png" />
      </a>
    </li>
  {% endfor %}
</ul>








