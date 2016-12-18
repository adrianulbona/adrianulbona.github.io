---
layout: page
title: About
---

{% if site.author.name %}
  <ul>
    <a href="https://github.com/{{ site.author.name  }}"><i class="fa fa-github fa-5x" style="margin:30px"></i></a>
    <a href="https://twitter.com/{{ site.author.name }}"><i class="fa fa-twitter fa-5x" style="margin:30px"></i></a>
    <a href="https://linkedin.com/in/{{ site.author.name }}"><i class="fa fa-linkedin fa-5x" style="margin:30px"></i></a>
  </ul>
{% endif %}