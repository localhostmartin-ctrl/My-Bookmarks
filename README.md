# My-Bookmarks
The Most Simple Self-hosting Bookmarking App

# My Private Bookmarks / 我的私人书签库

A lightweight, self-hosted bookmark management service tailored for NAS systems. It features a clean, Notion-inspired user interface and operates entirely on an embedded SQLite database, eliminating the need for complex external server setups.
本项目是一个轻量级的自托管书签管理服务，专为 NAS 系统量身定制。它拥有一个干净的、深受 Notion 启发的用户界面，并且完全依赖内置的 SQLite 数据库运行，免去了配置复杂外部数据库服务器的麻烦。

## ✨ Key Features / 核心功能

* **Notion-Style UI:** A highly minimalist, flat design that gets out of your way, featuring a native Dark Mode toggle for comfortable nighttime reading.
  **Notion 风格界面：** 极度极简的扁平化设计，绝不喧宾夺主，配备原生的黑暗模式切换开关，提供舒适的夜间阅读体验。
* **Infinite Nested Folders:** Create subfolders within subfolders without limits. Use the sidebar arrows to smoothly collapse or expand your hierarchy.
  **无限嵌套文件夹：** 无限制地在文件夹中创建子文件夹。使用侧边栏的箭头可以流畅地折叠或展开你的目录层级。
* **Native Drag-and-Drop:** Physically grab and rearrange folders or individual links. Drag a bookmark into a folder, or drop a subfolder into the "Root Zone" to reset its hierarchy.
  **原生拖放体验：** 物理抓取并重新排列文件夹或单个链接。将书签拖入文件夹，或者将子文件夹拖入“根目录区”以重置其层级。
* **Smart Scraper:** Paste a URL, hit enter, and the server acts as a digital scout to automatically fetch the website's real title for you.
  **智能抓取器：** 粘贴网址，按下回车，服务器会充当数字侦察兵，自动为你获取网站的真实标题。
* **Chrome HTML Import/Export:** Fully supports migrating your existing browser bookmarks via the standard Netscape HTML format, perfectly preserving your old folder structures.
  **Chrome HTML 导入/导出：** 全面支持通过标准的 Netscape HTML 格式迁移你现有的浏览器书签，完美保留你旧的文件夹结构。

## 🚀 Docker Compose Deployment / Docker Compose 部署指南

Using `docker-compose` is the recommended way to deploy this application on a Synology or fnOS NAS, as it ensures reproducible configurations.
强烈推荐使用 `docker-compose` 在群晖 (Synology) 或飞牛 (fnOS) NAS 上部署此应用程序，以确保配置的可完全重现。

### ⚠️ CRITICAL: The SQLite Volume Trap / 极其重要的警告：SQLite 卷映射陷阱
Before running the compose file, you **must manually create an empty database file**. If you do not, Docker will create a folder named `bookmarks.db`, which will crash the application.
在运行 compose 文件之前，你**必须手动创建一个空的数据库文件**。如果不这样做，Docker 会创建一个名为 `bookmarks.db` 的文件夹，这将导致应用程序崩溃。

```bash
# 1. Go to your deployment folder / 进入你的部署文件夹
cd /your/nas/path/bookmarks

# 2. Create the empty database file / 创建空的数据库文件
touch bookmarks.db
