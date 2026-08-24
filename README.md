# 日常集 · GitHub Pages 发布包

本目录包含可直接发布到 GitHub Pages 的文件：

- `index.html` —— 日常集单文件应用（已含全部 CSS/JS，零外部依赖，数据存浏览器 localStorage + Supabase 云端）
- `.nojekyll` —— 禁用 GitHub 的 Jekyll 处理，保证页面原样提供

## 发布步骤（只需做一次）

### 1. 注册并登录 GitHub
打开 https://github.com ，用邮箱注册一个免费账号并登录。

### 2. 新建仓库
- 右上角 `+` → `New repository`
- Repository name 填：`richangji`（或任意名字，这会成为链接的一部分）
- 选 **Public**（私有仓库 GitHub Pages 旧版需付费，免费账号用 Public 即可）
- 不要勾选 "Add a README file"（我们用本地这份）
- 点 `Create repository`

### 3. 上传文件
两种方式任选其一：

**方式 A（最简单，网页上传）：**
- 进入刚建好的仓库，点 `Add file` → `Upload files`
- 把本目录里的 `index.html` 和 `.nojekyll` 两个文件拖进去
- 下拉写个 commit 说明（如 `initial release`），点 `Commit changes`

**方式 B（Git 命令行，若你本机装了 git）：**
```bash
cd 本目录路径/github-pages
git init
git add index.html .nojekyll
git commit -m "initial release"
git branch -M main
git remote add origin https://github.com/你的用户名/richangji.git
git push -u origin main
```

### 4. 开启 GitHub Pages
- 仓库顶部进入 `Settings` → 左侧 `Pages`
- Source 选 `Deploy from a branch`
- Branch 选 `main` / `root` → 点 `Save`
- 等 1~2 分钟，页面顶部会出现你的访问链接：
  **https://你的用户名.github.io/richangji/**

### 5. 使用
- 打开上面的链接即可在任意设备浏览器使用（手机可"分享 → 添加到主屏幕"当 App 用）。
- 你的数据存在浏览器本地 + Supabase 云端，**与页面托管位置无关**，换托管也不丢。

## 后续更新
当你在「日常集」里改了功能、我重新生成 `index.html` 后：
- 把新的 `index.html` 覆盖本目录这份，再上传/commit 到仓库即可，链接不变。

## 与 CloudStudio 链接的关系
- CloudStudio 链接（`app.workbuddy.link`）和 GitHub Pages 链接是**两个独立入口**，打开的是同一份应用、同一份数据。
- GitHub Pages 由你自己的 GitHub 账号掌控，不会因为 WorkBuddy 平台策略变化而失效，适合作为"永久保险"地址。
- 建议两者都保留，互为备份。
