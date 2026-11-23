# 我的技术文档

欢迎访问我的个人文档网站。本网站使用 MkDocs 构建，通过 GitHub Actions 自动部署到 GitHub Pages。

- 作者：rtzsh
- 实践主题：静态文档自动部署
- 课程：开源软件开发实践 · 实践项目 2

## 这个网站是做什么的

这是一个用 Markdown 写成的四页文档站。我只需要编辑 `docs/` 目录下的 `.md` 文件并推送到 `main` 分支，
GitHub Actions 就会自动完成"安装依赖 → 构建 → 部署"，几十秒后公开网站的内容随之更新。
整个过程不需要我手动执行 `mkdocs gh-deploy`，也不需要登录服务器上传文件。

!!! note "为什么要做这个练习"

    文档写作本身不难，难的是"写完还要发布"这一步。把发布流程固化成工作流之后，
    写作和发布就被解耦了：我关心的只有正文，发布由机器保证一致性。

## 页面导航

| 页面 | 内容 |
| --- | --- |
| [关于本项目](about.md) | 项目目标、技术组成与各部分职责 |
| [使用指南](guide.md) | 日常改文档、本地预览、触发部署的完整流程 |
| [API 参考](api.md) | 用文档方式描述的示例接口 |

## 我的体会

（这里是需要你自己写的一段话，两三句即可，例如：第一次 push 之后在 Actions 页面等了两分钟看到绿色对勾，
比自己手动打包上传省事很多；或者踩过的坑，比如 YAML 用了 Tab 缩进导致构建失败。）

## 快速开始

```bash
git clone https://github.com/rtzsh/my-docs.git
cd my-docs
python -m pip install -r requirements.txt
python -m mkdocs serve
```

自动部署验证：这是我第二次推送后更新的内容。
