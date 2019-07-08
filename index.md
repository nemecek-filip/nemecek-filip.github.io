---
layout: page
title: Filip Němeček - personal blog
tagline:
---
{% include JB/setup %}

### Welcome

Welcome everyone to my humble developer blog. It is currently very much under construction as I am trying to figure this Jekyll thing out. Stuff may be broken, proceed with caution.

## Posts

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>

---

### Contact

Feel free to get in touch over at Twitter [@nemecek_f][1], my DMs are open if you want to use private messages.




[1]: https://twitter.com/nemecek_f