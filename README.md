# ZerothRobot 文档站

本仓库负责把独立文档仓库 [`ZerothRobot/zerothrobot-docs`](https://github.com/ZerothRobot/zerothrobot-docs) 发布到 `https://zerothrobot.github.io/docs/`。产品文档内容和 MkDocs 配置由源文档仓库维护。

## 本地预览

```bash
python -m venv .venv
source .venv/bin/activate
python -m pip install -r ../zerothrobot-docs/requirements.txt
mkdocs serve -f ../zerothrobot-docs/mkdocs.yml
```

预览服务默认地址为 `http://127.0.0.1:8000/docs/`。

## 构建

```bash
mkdocs build --strict -f ../zerothrobot-docs/mkdocs.yml --site-dir "$PWD/public/docs"
```

网站生成在 `public/docs/`，Pages 发布产物以 `public/` 为根，因此线上入口是 `/docs/`。GitHub Actions 从公开的 `ZerothRobot/zerothrobot-docs` 获取源文件，并使用源仓库的 MkDocs 配置构建。

## 发布

文档源仓库的 Pull Request 会执行严格构建检查。文档主分支更新后可触发官网仓库发布，官网仓库也会每小时同步一次源文档。发布目标是 `https://zerothrobot.github.io/docs/`。
