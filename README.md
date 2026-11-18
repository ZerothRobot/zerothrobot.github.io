# ZerothRobot 文档站

基于 MkDocs 和 Material for MkDocs 的中文文档站框架。文档源文件位于 `docs/`，站点配置位于 `mkdocs.yml`。

## 本地预览

```bash
python -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
mkdocs serve
```

预览服务默认地址为 `http://127.0.0.1:8000/`。

## 构建

```bash
mkdocs build --strict
```

生成的网站位于 `public/docs/`，Pages 发布产物以 `public/` 为根，因此线上入口是 `/docs/`。GitHub Actions 会在 Pull Request 和 `main` 分支更新时执行严格构建检查。

## 发布

本仓库只在 `https://zerothrobot.github.io/docs/` 发布文档，不发布根路径首页。Pull Request 会执行严格构建检查；合并到 `main` 后会自动将 MkDocs 生成的网站发布到 GitHub Pages。品牌官网由另一个网站独立维护。
