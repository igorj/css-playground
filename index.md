---
layout: default
---

Here I experiment with different CSS3 features that I am using or plan to use in my projects:

[Generate content with :before and :after](/generated_content.html)


<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>