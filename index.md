---
layout: default
title: 首页
---

<div class="home">
  <section class="intro">
    <h1>你好，我是 {{ site.author.name }} 👋</h1>
    <p class="bio">{{ site.author.bio }}</p>
    {% if site.author.avatar %}
    <img src="{{ site.author.avatar }}" alt="Avatar" class="avatar">
    {% endif %}
  </section>

  <section class="recent-posts">
    <h2>📝 近期动态</h2>
    {% for post in site.posts limit: 3 %}
    <article class="post-preview">
      <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
      <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%Y年%m月%d日" }}</time>
      <p>{{ post.excerpt | strip_html | truncate: 150 }}</p>
    </article>
    {% endfor %}
    <a href="/blog/" class="btn">查看更多 →</a>
  </section>

  <section class="research-highlights">
    <h2>🔬 科研成果</h2>
    <ul>
      <li>发表论文 X 篇，其中第一作者 Y 篇</li>
      <li>研究领域：人工智能、机器学习、数据科学</li>
      <li>最新论文：<a href="#">Paper Title</a> (Conference/Journal 2024)</li>
    </ul>
    <a href="/research/" class="btn">查看详情 →</a>
  </section>

  <section class="projects-highlights">
    <h2>💻 代码项目</h2>
    <div class="project-grid">
      {% for post in site.categories.projects limit: 3 %}
      <div class="project-card">
        <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
        <p>{{ post.description }}</p>
      </div>
      {% endfor %}
    </div>
    <a href="/projects/" class="btn">查看更多项目 →</a>
  </section>
</div>
