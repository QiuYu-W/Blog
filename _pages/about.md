---
layout: default
title: 关于我
permalink: /about/
---

<div class="about-page">
  <header class="post-header">
    <h1 class="post-title">关于我</h1>
  </header>

  <article class="post-content">
    <section class="profile">
      {% if site.author.avatar %}
      <img src="{{ site.author.avatar }}" alt="{{ site.author.name }}" class="profile-avatar" style="width: 200px; height: 200px; border-radius: 50%; float: right; margin-left: 2rem; margin-bottom: 1rem;">
      {% endif %}
      
      <p>你好！我是 <strong>{{ site.author.name }}</strong>，{{ site.author.bio }}。</p>
      
      <p>我目前位于 {{ site.author.location }}，专注于人工智能、机器学习和数据科学领域的研究与应用开发。热爱开源技术，喜欢通过博客分享学习心得和技术经验。</p>
    </section>

    <section class="education">
      <h2>🎓 教育背景</h2>
      <ul>
        <li><strong>博士学位</strong> - 计算机科学与技术，XX 大学 (2020-2024)</li>
        <li><strong>硕士学位</strong> - 软件工程，XX 大学 (2017-2020)</li>
        <li><strong>学士学位</strong> - 计算机科学，XX 大学 (2013-2017)</li>
      </ul>
    </section>

    <section class="experience">
      <h2>💼 工作经历</h2>
      <ul>
        <li><strong>高级算法工程师</strong> - XX 科技公司 (2024-至今)
          <ul>
            <li>负责机器学习模型的研發与优化</li>
            <li>主导多个 AI 项目的落地实施</li>
          </ul>
        </li>
        <li><strong>研究助理</strong> - XX 大学实验室 (2020-2024)
          <ul>
            <li>参与国家级科研项目 3 项</li>
            <li>发表 SCI/EI 论文 10 余篇</li>
          </ul>
        </li>
      </ul>
    </section>

    <section class="research-interests">
      <h2>🔬 研究方向</h2>
      <ul>
        <li>深度学习与神经网络</li>
        <li>自然语言处理 (NLP)</li>
        <li>计算机视觉 (CV)</li>
        <li>强化学习</li>
        <li>数据挖掘与分析</li>
      </ul>
    </section>

    <section class="skills">
      <h2>💻 技术技能</h2>
      <ul>
        <li><strong>编程语言:</strong> Python, C++, Java, JavaScript</li>
        <li><strong>框架工具:</strong> PyTorch, TensorFlow, Scikit-learn, Pandas, NumPy</li>
        <li><strong>开发工具:</strong> Git, Docker, Linux, MySQL, MongoDB</li>
        <li><strong>其他:</strong> LaTeX, Markdown, Jupyter Notebook</li>
      </ul>
    </section>

    <section class="contact">
      <h2>📧 联系方式</h2>
      <ul>
        <li>Email: {{ site.author.email }}</li>
        <li>GitHub: <a href="{{ site.social.github }}" target="_blank">{{ site.social.github }}</a></li>
        {% if site.social.twitter %}
        <li>Twitter: <a href="{{ site.social.twitter }}" target="_blank">{{ site.social.twitter }}</a></li>
        {% endif %}
        {% if site.social.linkedin %}
        <li>LinkedIn: <a href="{{ site.social.linkedin }}" target="_blank">{{ site.social.linkedin }}</a></li>
        {% endif %}
        {% if site.social.google_scholar %}
        <li>Google Scholar: <a href="{{ site.social.google_scholar }}" target="_blank">查看学术主页</a></li>
        {% endif %}
      </ul>
    </section>
  </article>
</div>

<style>
.about-page section {
  margin-bottom: 2.5rem;
}

.about-page h2 {
  color: var(--primary-color);
  border-bottom: 2px solid var(--border-color);
  padding-bottom: 0.5rem;
  margin-bottom: 1rem;
}

.about-page ul {
  list-style-position: outside;
  margin-left: 1.5rem;
}

.about-page li {
  margin-bottom: 0.5rem;
}

.profile-avatar {
  border: 4px solid var(--border-color);
  box-shadow: 0 4px 8px rgba(0,0,0,0.1);
}

@media (max-width: 768px) {
  .profile-avatar {
    float: none;
    display: block;
    margin: 0 auto 1.5rem;
  }
}
</style>
