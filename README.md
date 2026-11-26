# my-docs

用 MkDocs Material 编写的四页文档站，通过 GitHub Actions 自动构建并部署到 GitHub Pages。

- 网站地址：https://rtzsh.github.io/my-docs/
- 实验报告：[个人实验报告](report/README.md)
- Pi Agent 实践课 1-5：[实践课作业](practice/README.md)
- 作者：rtzsh

## 项目简介

源码只有 Markdown 和一份 `mkdocs.yml`。推送到 `main` 后，工作流依次执行
"检出源码 → 安装 Python 与依赖 → `mkdocs build --strict` → 上传 `site/` → 部署到 Pages"，
不需要手动构建或手动上传。

## 目录结构

```text
.
├── .github/workflows/deploy.yml   # 自动构建与部署
├── docs/                          # 网站内容（四页 Markdown）
├── report/                        # 实验报告与过程截图
├── mkdocs.yml                     # 站点与导航配置
├── requirements.txt               # MkDocs 及主题版本范围
└── README.md
```

## 本地预览

```bash
python -m venv .venv
.\.venv\Scripts\Activate.ps1      # Windows PowerShell
python -m pip install -r requirements.txt
python -m mkdocs serve            # 打开 http://127.0.0.1:8000/
```

严格构建（把警告当错误，用于推送前自检）：

```bash
python -m mkdocs build --strict
```
