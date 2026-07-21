---
layout: default
title: 博客
permalink: /blog/
---

<div class="blog-page">
  <header class="post-header">
    <h1 class="post-title">📝 博客文章</h1>
    <p class="page-description">分享技术心得、学习笔记和生活感悟</p>
  </header>

  <article class="post-content">
    {% if site.posts.size > 0 %}
      <div class="posts-list">
        {% for post in paginator.posts %}
          <article class="post-item">
            <header class="post-item-header">
              <h2 class="post-item-title">
                <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
              </h2>
              <div class="post-item-meta">
                <time datetime="{{ post.date | date_to_xmlschema }}">
                  📅 {{ post.date | date: "%Y年%m月%d日" }}
                </time>
                {% if post.categories %}
                  <span class="category">📂 {{ post.categories.first }}</span>
                {% endif %}
              </div>
            </header>

            {% if post.description %}
              <p class="post-item-description">{{ post.description }}</p>
            {% else %}
              <p class="post-item-excerpt">{{ post.excerpt | strip_html | truncate: 200 }}</p>
            {% endif %}

            <footer class="post-item-footer">
              <a href="{{ post.url | relative_url }}" class="read-more">阅读全文 →</a>
              {% if post.tags %}
                <div class="post-tags">
                  {% for tag in post.tags limit: 5 %}
                    <span class="tag">#{{ tag }}</span>
                  {% endfor %}
                </div>
              {% endif %}
            </footer>
          </article>
        {% endfor %}
      </div>

      <!-- 分页导航 -->
      <div class="pagination">
        {% if paginator.previous_page %}
          <a href="{{ paginator.previous_page_path | relative_url }}" class="btn btn-outline">← 上一页</a>
        {% else %}
          <span class="btn disabled">← 上一页</span>
        {% endif %}

        <span class="page-number">第 {{ paginator.page }} 页 / 共 {{ paginator.total_pages }} 页</span>

        {% if paginator.next_page %}
          <a href="{{ paginator.next_page_path | relative_url }}" class="btn">下一页 →</a>
        {% else %}
          <span class="btn disabled">下一页 →</span>
        {% endif %}
      </div>
    {% else %}
      <div class="no-posts">
        <h3>🎉 即将更新</h3>
        <p>博客文章正在准备中，敬请期待！</p>
        <p>你可以先浏览我的<a href="/about/">个人介绍</a>、<a href="/research/">科研成果</a>或<a href="/projects/">代码项目</a>。</p>
      </div>
    {% endif %}

    <!-- 分类标签云 -->
    {% if site.posts.size > 0 %}
      <section class="categories-section">
        <h2>📚 文章分类</h2>
        <div class="categories-cloud">
          {% assign categories = site.categories %}
          {% for category in categories %}
            {% assign category_name = category | first %}
            {% assign category_count = category | last | size %}
            <a href="#{{ category_name }}" class="category-tag">
              {{ category_name }} ({{ category_count }})
            </a>
          {% endfor %}
        </div>
      </section>
    {% endif %}
  </article>
</div>

<style>
.blog-page .page-description {
  color: var(--light-text);
  font-size: 1.1rem;
  margin-top: 0.5rem;
}

.posts-list {
  margin: 2rem 0;
}

.post-item {
  background: var(--bg-color);
  border: 1px solid var(--border-color);
  border-radius: 8px;
  padding: 2rem;
  margin-bottom: 2rem;
  transition: all 0.3s ease;
}

.post-item:hover {
  border-color: var(--primary-color);
  box-shadow: 0 4px 12px rgba(0,0,0,0.08);
  transform: translateY(-2px);
}

.post-item-title {
  margin-bottom: 0.5rem;
}

.post-item-title a {
  color: var(--text-color);
  font-size: 1.8rem;
  line-height: 1.3;
}

.post-item-title a:hover {
  color: var(--primary-color);
  text-decoration: none;
}

.post-item-meta {
  display: flex;
  gap: 1.5rem;
  color: var(--light-text);
  font-size: 0.9rem;
  margin-bottom: 1rem;
}

.category {
  background: var(--primary-color);
  color: white;
  padding: 0.2rem 0.6rem;
  border-radius: 4px;
  font-size: 0.85rem;
}

.post-item-description,
.post-item-excerpt {
  color: var(--light-text);
  line-height: 1.7;
  margin-bottom: 1rem;
}

.post-item-footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  gap: 1rem;
  padding-top: 1rem;
  border-top: 1px solid var(--border-color);
}

.read-more {
  color: var(--primary-color);
  font-weight: 500;
  transition: all 0.3s ease;
}

.read-more:hover {
  color: var(--secondary-color);
  text-decoration: none;
}

.post-tags {
  display: flex;
  gap: 0.5rem;
  flex-wrap: wrap;
}

.post-tags .tag {
  font-size: 0.85rem;
  padding: 0.25rem 0.6rem;
  background: var(--light-bg);
  color: var(--light-text);
  border-radius: 4px;
}

/* 分页 */
.pagination {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 1.5rem;
  margin: 3rem 0;
  padding: 2rem 0;
}

.page-number {
  color: var(--light-text);
  font-weight: 500;
}

.btn.disabled {
  opacity: 0.5;
  cursor: not-allowed;
  pointer-events: none;
}

/* 无文章提示 */
.no-posts {
  text-align: center;
  padding: 4rem 2rem;
  background: var(--light-bg);
  border-radius: 8px;
  margin: 2rem 0;
}

.no-posts h3 {
  font-size: 1.8rem;
  color: var(--primary-color);
  margin-bottom: 1rem;
}

.no-posts p {
  color: var(--light-text);
  margin: 0.5rem 0;
}

/* 分类区域 */
.categories-section {
  margin-top: 4rem;
  padding-top: 3rem;
  border-top: 1px solid var(--border-color);
}

.categories-section h2 {
  margin-bottom: 1.5rem;
  color: var(--primary-color);
}

.categories-cloud {
  display: flex;
  flex-wrap: wrap;
  gap: 0.75rem;
}

.category-tag {
  display: inline-block;
  padding: 0.5rem 1rem;
  background: var(--light-bg);
  color: var(--text-color);
  border-radius: 6px;
  border: 1px solid var(--border-color);
  transition: all 0.3s ease;
  font-weight: 500;
}

.category-tag:hover {
  background: var(--primary-color);
  color: white;
  border-color: var(--primary-color);
  text-decoration: none;
  transform: translateY(-2px);
}

@media (max-width: 768px) {
  .post-item-title a {
    font-size: 1.5rem;
  }

  .post-item-meta {
    flex-direction: column;
    gap: 0.5rem;
  }

  .post-item-footer {
    flex-direction: column;
    align-items: flex-start;
  }

  .pagination {
    flex-direction: column;
    gap: 1rem;
  }
}
</style>
