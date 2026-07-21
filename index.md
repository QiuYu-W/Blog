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

<style>
.home section {
  margin-bottom: 3rem;
}

.intro {
  text-align: center;
  padding: 3rem 0;
}

.intro h1 {
  font-size: 2.5rem;
  color: var(--primary-color);
  margin-bottom: 1rem;
}

.bio {
  font-size: 1.2rem;
  color: var(--light-text);
  max-width: 600px;
  margin: 0 auto;
}

.avatar {
  width: 150px;
  height: 150px;
  border-radius: 50%;
  margin: 2rem auto;
  border: 4px solid var(--border-color);
  box-shadow: 0 4px 8px rgba(0,0,0,0.1);
}

.recent-posts h2,
.research-highlights h2,
.projects-highlights h2 {
  color: var(--primary-color);
  margin-bottom: 1.5rem;
  border-bottom: 2px solid var(--border-color);
  padding-bottom: 0.5rem;
}

.post-preview {
  background: var(--light-bg);
  padding: 1.5rem;
  border-radius: 8px;
  margin-bottom: 1rem;
  transition: all 0.3s ease;
}

.post-preview:hover {
  transform: translateY(-3px);
  box-shadow: 0 4px 12px rgba(0,0,0,0.08);
}

.post-preview h3 {
  margin-bottom: 0.5rem;
}

.post-preview h3 a {
  color: var(--text-color);
}

.post-preview h3 a:hover {
  color: var(--primary-color);
  text-decoration: none;
}

.post-preview time {
  display: block;
  color: var(--light-text);
  font-size: 0.9rem;
  margin-bottom: 0.5rem;
}

.post-preview p {
  color: var(--light-text);
  line-height: 1.6;
}

.research-highlights ul {
  background: var(--light-bg);
  padding: 2rem;
  border-radius: 8px;
  list-style-position: inside;
}

.research-highlights li {
  margin-bottom: 0.5rem;
  color: var(--light-text);
}

.project-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 1.5rem;
  margin-bottom: 1.5rem;
}

.project-card {
  background: var(--light-bg);
  padding: 1.5rem;
  border-radius: 8px;
  border: 1px solid var(--border-color);
  transition: all 0.3s ease;
}

.project-card:hover {
  border-color: var(--primary-color);
  transform: translateY(-3px);
}

.project-card h3 {
  color: var(--primary-color);
  margin-bottom: 0.5rem;
}

.project-card h3 a {
  color: inherit;
}

.project-card h3 a:hover {
  text-decoration: none;
}

.project-card p {
  color: var(--light-text);
  font-size: 0.95rem;
}

.btn {
  display: inline-block;
  padding: 0.75rem 1.5rem;
  background: var(--primary-color);
  color: white;
  border-radius: 6px;
  font-weight: 500;
  transition: all 0.3s ease;
  border: none;
  cursor: pointer;
}

.btn:hover {
  background: var(--secondary-color);
  color: white;
  text-decoration: none;
  transform: translateY(-2px);
}

@media (max-width: 768px) {
  .intro h1 {
    font-size: 2rem;
  }

  .bio {
    font-size: 1rem;
  }

  .project-grid {
    grid-template-columns: 1fr;
  }
}
</style>
