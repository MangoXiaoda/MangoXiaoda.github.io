# Wind Dream CMS Blog

这是一个 Hugo + Dream 主题 + Sveltia/Decap 兼容配置的个人博客脚手架。

## 本地启动

```bash
npm install
npm run dev:all
```

前台地址：

```text
http://127.0.0.1:1313/
```

后台地址：

```text
http://127.0.0.1:1313/admin/
```

本地后台依赖 `decap-server`，它会把 CMS 的改动写回当前 Git 仓库。

线上后台使用 Sveltia CMS。打开 `/admin/` 后可以选择使用 GitHub token 登录，token 至少需要当前仓库的 `Contents: Read and write` 权限；如果要改 workflow 文件，还需要 `Workflows: Read and write`。

## 发布前要改

1. 在 `hugo.toml` 里把 `baseURL` 改成你的真实域名。
2. 在 `static/admin/config.yml` 里把 `repo` 改成你的 GitHub 仓库，例如 `yourname/wind-dream-cms-blog`。
3. 如果要多人用“GitHub 登录”按钮登录后台，需要配置 OAuth proxy，并打开 `base_url`。
4. 如果要评论，部署 Waline 后取消 `hugo.toml` 里的 `waline` 和 `walineServer` 注释。

## 目录说明

```text
content/posts/        文章内容
content/about/        首页背面的关于卡片，后台默认编辑 intro.md
static/admin/         CMS 后台
static/img/uploads/   后台上传的图片
themes/hugo-theme-dream/ Dream 主题，已作为项目文件内置
```

## 构建

```bash
npm run build
```

生成的静态文件在 `public/`。
