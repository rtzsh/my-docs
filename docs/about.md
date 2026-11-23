# 关于本项目

## 项目目标

实现从 Markdown 文档到公开网站的自动化发布：写作者只提交源代码，构建与托管交给流水线。

## 技术组成

| 工具 | 作用 |
| --- | --- |
| Markdown | 编写文档内容，纯文本、易版本管理 |
| MkDocs Material | 将 Markdown 构建成静态网站（HTML/CSS/JS） |
| GitHub Actions | 自动执行安装、构建和部署 |
| GitHub Pages | 托管并提供网站访问地址 |

## 三样东西的关系

理解这个实践的关键，是分清"源码""产物""托管"三者：

```text
docs/*.md  +  mkdocs.yml        ← 我写的源码（提交进仓库，纳入版本管理）
        │
        │  mkdocs build --strict
        ▼
site/  （index.html、assets/…） ← 构建产物（每次重新生成，写进 .gitignore）
        │
        │  upload-pages-artifact → deploy-pages
        ▼
https://YOUR-USERNAME.github.io/my-docs/   ← GitHub Pages 托管的公开网站
```

- `docs/` 是**输入**，人和 Git 都关心它；
- `site/` 是**输出**，机器生成、可随时重建，所以不提交、不手改；
- Pages 是**出口**，它只负责把产物按 HTTP 提供出去。

!!! tip "一句话记住"

    源码进仓库，产物进制品（artifact），网站由 Pages 托管。

## 为什么用官方 Pages Actions

传统做法是把 `site/` 推到 `gh-pages` 分支再让 Pages 读分支。这条老路要维护一条额外的分支，
还要处理分支写权限。官方方案改为"上传制品 + 部署"，产物不落地成分支，权限也更小：
`build` 任务只需要 `contents: read`，只有 `deploy` 任务拿到 `pages: write` 和 `id-token: write`。

返回 [首页](index.md) 或继续看 [使用指南](guide.md)。
