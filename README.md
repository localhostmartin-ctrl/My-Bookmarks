# My-Bookmarks
The Most Simple Self-hosting Bookmarking App

# My Private Bookmarks

A lightweight, self-hosted bookmark management service tailored for NAS systems. It features a clean, Notion-inspired user interface and operates entirely on an embedded SQLite database, eliminating the need for complex external server setups.

## ✨ Key Features

* **Notion-Style UI:** A highly minimalist, flat design that gets out of your way, featuring a native Dark Mode toggle for comfortable nighttime reading.
* **Infinite Nested Folders:** Create subfolders within subfolders without limits. Use the sidebar arrows to smoothly collapse or expand your hierarchy.
* **Native Drag-and-Drop:** Physically grab and rearrange folders or individual links. Drag a bookmark into a folder, or drop a subfolder into the "Root Zone" to reset its hierarchy.
* **Smart Scraper:** Paste a URL, hit enter, and the server acts as a digital scout to automatically fetch the website's real title for you.
* **Chrome HTML Import/Export:** Fully supports migrating your existing browser bookmarks via the standard Netscape HTML format, perfectly preserving your old folder structures.

## 🚀 Docker Compose Deployment

Using `docker-compose` is the recommended way to deploy this application on a Synology or fnOS NAS, as it ensures reproducible configurations.

### ⚠️ CRITICAL: The SQLite Volume Trap
Before running the compose file, you **must manually create an empty database file**. If you do not, Docker will create a folder named `bookmarks.db`, which will crash the application.

```bash
# 1. Go to your deployment folder
cd /your/nas/path/bookmarks

# 2. Create the empty database file
touch bookmarks.db
