# netbuffer 的个人博客

> 认准了，就去做，不跟风，不动摇

记录从 2014 年至今的技术成长历程，涵盖 Java / Spring Cloud / AI 大模型 / 全栈开发 与 DevOps。

## 🌐 访问地址

| 平台 | 地址 | 说明 |
|------|------|------|
| GitHub Pages | [https://netbuffer.github.io](https://netbuffer.github.io) | 主博客（GitHub Actions 自动化部署） |

---

## 🛠 技术架构

- **核心引擎**：[Hexo](https://hexo.io/) v8.1.2（Node.js 驱动的高性能静态博客框架）
- **主题**：[Butterfly](https://butterfly.js.org/) v5.7.0（现代化美观响应式主题）
- **包管理**：[pnpm](https://pnpm.io/) v11.x
- **CI / CD**：**GitHub Actions** 原生自动化构建与发布（无多余分支，推送即上线）
- **托管服务**：GitHub Pages（基于 Actions Artifact 直推）

---

## 📁 项目目录结构

```
netbuffer/
├── .github/
│   └── workflows/
│       └── deploy.yml          # GitHub Actions 自动化部署工作流
├── source/
│   ├── _posts/                 # 博客文章（Markdown 原稿）
│   │   ├── 2026-ai-technology-trends.md
│   │   ├── api-gateway.md
│   │   ├── load-balance-test.md
│   │   ├── spring-boot-bootstrap_table.md
│   │   └── spring-cloud-demo.md
│   ├── about/                  # 关于页面
│   ├── categories/             # 分类汇总聚合页
│   ├── tags/                   # 标签云汇总聚合页
│   └── img/                    # 静态图片与图标资源（Banner、封面、背景、Favicon 等）
├── _config.yml                 # Hexo 全局站点配置
├── _config.butterfly.yml       # Butterfly 主题独占配置
├── package.json                # 项目依赖与运行脚本
├── pnpm-lock.yaml              # 依赖锁定文件
└── .gitignore                  # Git 忽略规则（已自动忽略 public/ 和 node_modules/）
```

---

## 💻 本地开发与写作

### 1. 运行本地开发服务器

```bash
# 安装依赖（首次运行）
pnpm install

# 启动本地预览（支持热更新）
pnpm run server
# 或 npx hexo server
```
浏览器访问：`http://localhost:4000`

### 2. 新建文章

```bash
npx hexo new "我的新文章"
```
会在 `source/_posts/我的新文章.md` 生成模板，编辑该 Markdown 文件即可。

### 3. 本地构建测试（可选）

```bash
pnpm run clean && pnpm run build
```

---

## 🚀 自动化部署工作流（GitHub Actions）

本项目采用现代化的 **GitHub Actions 直推部署**，无需额外创建 `gh-pages` 分支，也无需手动编译上传 HTML 文件。

### 部署流程：
1. 本地写完文章或修改配置后，直接提交推送到 GitHub：
   ```bash
   git add .
   git commit -m "feat: 发布新文章"
   git push origin master
   ```
2. GitHub Actions 检测到 `master` 分支推送，自动运行 [deploy.yml](.github/workflows/deploy.yml)：
   - 自动安装 Node.js 20 与 pnpm 缓存
   - 执行 `pnpm install` 与 `hexo generate`
   - 将生成的静态站点自动发布至 GitHub Pages
3. 全程约 30 秒，自动化完成。

### ⚠️ GitHub 仓库初次启用设置（仅需设置一次）
1. 打开 GitHub 仓库页面，点击 **Settings**。
2. 在左侧菜单找到 **Pages**（即 `Settings -> Pages`）。
3. 在 **Build and deployment** 下方的 **Source** 下拉菜单中，选择：
   👉 **`GitHub Actions`**（不要选 *Deploy from a branch*）。
4. 保存即可！以后每次 push 代码都会自动部署。

---

## 📝 升级历程

- **2014 - 2016**：基于 Hexo 早期版本搭建，使用 Huno 主题，记录 Java / SSM / 前端框架学习。
- **2019 - 2020**：更新 Spring Boot、Spring Cloud 微服务系列实战文章。
- **2026-09-26**：
  - 升级至 **Hexo 8.x + Butterfly 5.7.0** 主题。
  - 引入 **GitHub Actions** CI/CD 自动化流水线，淘汰旧版手动分支编译流程。
  - 项目重构为纯源码单分支工程，干净高效。
  - 发布全新《2026 年人工智能技术演进与产业落地全景展望》万字深度分析文章。
