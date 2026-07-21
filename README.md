# 个人学术博客网站

这是一个基于 Jekyll 构建的个人学术博客网站，专为研究人员和开发者设计，用于展示个人信息、科研成果、代码项目和博客文章。

## ✨ 特点

- 🎯 **简洁易用** - 只需编辑 Markdown 文件即可更新内容
- 📱 **响应式设计** - 完美适配桌面和移动设备
- 🔬 **学术导向** - 专门的科研成果展示页面
- 💻 **项目展示** - 代码项目卡片式布局
- 📝 **博客功能** - 支持分类、标签和评论
- 🚀 **GitHub Pages** - 免费托管，自动部署

## 📁 目录结构

```
.
├── _config.yml           # 网站配置文件
├── _layouts/             # 页面模板
│   └── default.html      # 默认布局模板
├── _pages/               # 静态页面
│   ├── about.md          # 关于我
│   ├── research.md       # 科研成果
│   ├── projects.md       # 代码项目
│   └── blog.md           # 博客列表
├── _posts/               # 博客文章
│   └── 2024-01-15-welcome.md
├── assets/               # 静态资源
│   ├── css/
│   │   └── style.css     # 样式文件
│   └── images/           # 图片资源
├── index.md              # 首页
└── README.md             # 说明文档
```

## 🚀 快速开始

### 1. Fork 并克隆仓库

```bash
git clone https://github.com/your-username/your-username.github.io.git
cd your-username.github.io
```

### 2. 个性化配置

编辑 `_config.yml` 文件，修改以下信息：

```yaml
title: "你的姓名"
description: "你的个人简介"
author:
  name: Your Name
  email: your.email@example.com
  bio: "你的个人标签"
social:
  github: https://github.com/your-username
  twitter: https://twitter.com/your-username
  google_scholar: https://scholar.google.com/...
```

### 3. 添加头像（可选）

将你的头像图片命名为 `avatar.jpg` 并放入 `assets/images/` 目录。

### 4. 本地预览

安装 Jekyll 后运行：

```bash
bundle install
bundle exec jekyll serve
```

在浏览器中访问 `http://localhost:4000`

### 5. 部署到 GitHub Pages

```bash
git add .
git commit -m "初始化博客网站"
git push origin main
```

访问 `https://your-username.github.io` 即可看到你的网站！

## 📝 如何更新内容

### 添加博客文章

在 `_posts/` 目录创建新文件，命名格式为 `YYYY-MM-DD-title.md`：

```markdown
---
layout: default
title: 文章标题
date: 2024-01-20 10:00:00 +0800
categories: [技术，教程]
tags: [Python, AI]
description: "文章简介"
---

这里是文章内容...
```

### 更新科研成果

编辑 `_pages/research.md`，添加新的论文和项目信息。

### 更新项目展示

编辑 `_pages/projects.md`，添加新的项目卡片。

### 更新个人信息

编辑 `_pages/about.md`，修改教育背景、工作经历等信息。

## ⚙️ 高级配置

### 启用评论系统

在 `_config.yml` 中配置 utterances：

```yaml
comments:
  enabled: true
  repository: "your-username/your-username.github.io"
  issue-term: "pathname"
  label: "comments"
  theme: "github-light"
```

### 添加 Google Analytics

在 `_config.yml` 中添加：

```yaml
google_analytics: UA-XXXXXXXXX-X
```

## 🎨 自定义样式

编辑 `assets/css/style.css` 来自定义网站外观。主要颜色变量：

- 主色调：`#0366d6` (GitHub 蓝)
- 背景色：`#f9f9f9`
- 文字色：`#333`

## 📄 许可证

MIT License

## 🤝 贡献

欢迎提交 Issue 和 Pull Request！

## 📧 联系方式

如有问题，请通过以下方式联系：

- Email: your.email@example.com
- GitHub Issues: [提交问题](https://github.com/your-username/your-username.github.io/issues)

---

**祝你使用愉快！** 🎉
