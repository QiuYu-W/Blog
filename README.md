# 个人学术博客网站

这是一个基于 Jekyll 构建的个人学术博客网站，专为研究人员、开发者和技术爱好者设计。

## ✨ 功能特点

- 📝 **完整的博客系统** - 支持文章分类、标签、分页和评论
- 🔬 **学术导向设计** - 专门展示论文、研究项目和专利成果
- 💻 **项目展示** - 开源项目和技术作品展示页面
- 📱 **响应式设计** - 完美适配桌面端和移动端
- 🎨 **现代化 UI** - 简洁美观的界面设计
- 🔍 **SEO 优化** - 内置 SEO 标签，提升搜索引擎排名
- 🚀 **自动部署** - 通过 GitHub Actions 自动构建和部署

## 📁 目录结构

```
.
├── _config.yml           # 网站配置文件
├── Gemfile               # Ruby 依赖文件
├── index.md              # 首页
├── _layouts/
│   └── default.html      # 默认布局模板
├── _pages/
│   ├── about.md          # 关于我页面
│   ├── research.md       # 科研成果页面
│   ├── projects.md       # 代码项目页面
│   └── blog.md           # 博客列表页面
├── _posts/
│   └── 2024-01-15-welcome.md  # 示例博客文章
├── assets/
│   └── css/
│       └── style.css     # 样式文件
└── .github/
    └── workflows/
        └── jekyll.yml    # GitHub Actions 配置
```

## 🚀 快速开始

### 本地预览

1. **安装 Ruby 和 Bundler**
   ```bash
   # macOS
   brew install ruby
   gem install bundler

   # Ubuntu/Debian
   sudo apt-get install ruby-full
   gem install bundler
   ```

2. **安装依赖**
   ```bash
   bundle install
   ```

3. **启动本地服务器**
   ```bash
   bundle exec jekyll serve
   ```

4. **访问网站**
   打开浏览器访问 `http://localhost:4000`

### GitHub Pages 部署

1. **Fork 或克隆此仓库**

2. **修改配置文件 `_config.yml`**
   - 更新 `title`、`description` 等基本信息
   - 填写你的个人信息（姓名、邮箱、简介等）
   - 配置社交媒体链接
   - 如有需要，设置 `baseurl`（例如：`/my-blog`）

3. **推送代码到 GitHub**
   ```bash
   git add .
   git commit -m "Initial commit"
   git push origin main
   ```

4. **启用 GitHub Pages**
   - 进入仓库 Settings → Pages
   - Source 选择 "Deploy from a branch"
   - Branch 选择 "main"，文件夹选择 "/ (root)"
   - 点击 Save

5. **访问你的网站**
   等待几分钟后，访问 `https://your-username.github.io`

## ⚙️ 配置说明

### 基本信息 (`_config.yml`)

```yaml
title: "你的姓名 | 个人学术博客"
description: "研究人员、开发者、技术爱好者 - 分享科研成果与编程心得"
baseurl: ""  # 如果有子路径，例如 /blog
url: "https://your-username.github.io"
```

### 作者信息

```yaml
author:
  name: Your Name
  email: your.email@example.com
  bio: "人工智能研究者 | 开源爱好者 | 技术博主"
  avatar: "/assets/images/avatar.jpg"
  location: "北京，中国"
  website: "https://your-website.com"
```

### 社交媒体链接

```yaml
social:
  github: https://github.com/your-username
  twitter: https://twitter.com/your-username
  linkedin: https://linkedin.com/in/your-username
  google_scholar: https://scholar.google.com/citations?user=YOUR_ID
  zhihu: https://www.zhihu.com/people/your-zhihu
```

## 📝 写作指南

### 创建新文章

在 `_posts/` 目录下创建新文件，命名格式为 `YYYY-MM-DD-title.md`：

```markdown
---
layout: default
title: 文章标题
date: 2024-01-15 10:00:00 +0800
categories: [技术，生活]
tags: [Jekyll, GitHub Pages]
description: "文章描述"
---

这里是文章内容...
```

### 支持的 Markdown 语法

- 标题：`# H1`, `## H2`, `### H3`
- 粗体：`**text**`
- 斜体：`*text*`
- 链接：`[text](url)`
- 图片：`![alt](url)`
- 代码块：\`\`\`language ... \`\`\`
- 引用：`> text`
- 列表：`- item` 或 `1. item`

## 🎨 自定义样式

编辑 `assets/css/style.css` 文件来自定义网站样式。主要 CSS 变量：

```css
:root {
  --primary-color: #0366d6;    /* 主色调 */
  --secondary-color: #58a6ff;  /* 辅助色 */
  --text-color: #333;          /* 文字颜色 */
  --light-text: #666;          /* 浅色文字 */
  --bg-color: #fff;            /* 背景色 */
  --light-bg: #f9f9f9;         /* 浅色背景 */
  --border-color: #eaeaea;     /* 边框颜色 */
}
```

## 🔧 高级功能

### 评论系统

使用 Utterances 评论系统（基于 GitHub Issues）：

1. 在你的仓库中启用 Issues
2. 在 `_config.yml` 中配置：

```yaml
comments:
  enabled: true
  repository: "your-username/your-username.github.io"
  issue_term: "pathname"
  label: "comments"
  theme: "github-light"
```

### Google Analytics

在 `_config.yml` 中添加：

```yaml
google_analytics: UA-XXXXXXXXX-X
```

## 📄 许可证

MIT License

## 🤝 贡献

欢迎提交 Issue 和 Pull Request！

## 📧 联系方式

- Email: your.email@example.com
- GitHub: [@your-username](https://github.com/your-username)

---

**Happy Blogging! 🎉**
