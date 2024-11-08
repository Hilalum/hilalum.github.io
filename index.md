---
layout: home
title: "首页"
---

# 欢迎来到我的博客

这是我的博客首页，在这里你可以看到我的最新文章和分享。

<div class="posts">
  {% for post in site.posts %}
    <article>
      <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
      <p>{{ post.excerpt }}</p>
      <a href="{{ post.url }}">阅读全文</a>
    </article>
  {% endfor %}
</div>