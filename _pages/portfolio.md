---
title: "Portfolio"
permalink: /portfolio/
author_profile: true
header:
  image: "/images/Puzzle.jpeg"
---
<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
