# 使用指南

## 日常写作流程

1. 修改 `docs` 目录中的 Markdown 文件。
2. 在本地预览并检查页面及链接。
3. 提交修改并推送到 `main` 分支。
4. 在 Actions 页面查看构建与部署状态。
5. 打开网站检查内容是否更新。

## 常用命令

| 命令 | 用途 |
| --- | --- |
| `python -m mkdocs serve` | 本地预览，改文件自动刷新 |
| `python -m mkdocs build --strict` | 构建并严格检查警告（把警告当错误） |
| `python -m mkdocs build` | 只构建，不因警告失败 |

```bash
# 1. 进入虚拟环境（Windows PowerShell）
.\.venv\Scripts\Activate.ps1

# 2. 安装依赖
python -m pip install -r requirements.txt

# 3. 本地预览，浏览器打开 http://127.0.0.1:8000/
python -m mkdocs serve

# 4. 提交前先做一次严格构建，确认没有坏链接
python -m mkdocs build --strict
```

## 提交与推送

```bash
git status                          # 确认没有把 .venv/ 或 site/ 加进来
git add docs mkdocs.yml
git diff --staged                   # 推送前再看一眼改了什么
git commit -m "更新使用指南"
git push origin main
```

推送后到仓库的 **Actions** 页面，能看到一次 `Deploy MkDocs to GitHub Pages` 运行：
`build` 绿了才会执行 `deploy`，两个都绿了网站才更新。

!!! warning "两个常见坑"

    1. `mkdocs.yml` 里 `nav` 的路径是相对 `docs/` 的，写 `index.md` 而不是 `docs/index.md`。
    2. YAML 只能用空格缩进，混入 Tab 会直接构建失败，报错信息往往指向行号而不是"Tab"。

## 触发条件

工作流只在这些文件被推送到 `main` 时运行：`docs/**`、`mkdocs.yml`、`requirements.txt`、
`.github/workflows/deploy.yml`。只改 `report/` 或根目录 `README.md` **不会**触发部署——
这是 `paths` 过滤器在起作用，属于预期行为。

需要重跑时，不必改文件，可以在 Actions 页面点 **Run workflow**（对应 `workflow_dispatch`）。

回到 [首页](index.md)，或查看 [API 参考](api.md)。
