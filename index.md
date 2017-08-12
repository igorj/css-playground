---
layout: default
---

Here I experiment with different CSS3 features that I am using or plan to use in my projects:

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ site.url }}{{ site.baseurl}}{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>