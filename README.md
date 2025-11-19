# 🎯 Google Colab Torrent Downloader (2025 Working)

A **100% working torrent downloader inside Google Colab** (Python 3.11 compatible).  
This script downloads any torrent **directly into your Google Drive** and shows **live download progress**.

Colab removed `libtorrent` support in 2025, so this project uses **WebTorrent CLI** with Node.js — the only fully working method.

---

## 🚀 Features
- ✔ **Download torrents using magnet links**
- ✔ **Saves directly to Google Drive**
- ✔ **Shows live progress, speed & status**
- ✔ **Works on all 2025+ Colab runtimes**
- ✔ **No libtorrent or Python wheels required**
- ✔ Simple & stable

---

## 📦 Requirements
This project runs entirely in **Google Colab**.

- Google Drive  
- Google Colab account (free)  
- Internet connection  

---

## 📁 Folder Structure

Your downloaded files will be saved here:

```
/MyDrive/torrent_downloads/
```

---

## 🧰 Installation & Setup

### 1. Mount Google Drive
```python
from google.colab import drive
drive.mount('/content/drive')
```

---

### 2. Install WebTorrent CLI
```bash
!npm install -g webtorrent-cli
```

---

### 3. Prepare the download folder
```python
import os
os.makedirs('/content/drive/MyDrive/torrent_downloads', exist_ok=True)
```

---

## ▶️ Run the Torrent Downloader

```python
from google.colab import drive
drive.mount('/content/drive')

import os

# Create folder
save_path = "/content/drive/MyDrive/torrent_downloads"
os.makedirs(save_path, exist_ok=True)

# Ask user for magnet link
magnet = input("🔗 Enter your MAGNET LINK: ")

print("\n⬇️ Starting Torrent Download...\n")

# Run WebTorrent with progress display
!webtorrent download "{magnet}" --out "{save_path}" --verbose
```

---

## 📊 Example Output
```
🔗 Enter your MAGNET LINK: magnet:?xt=urn:btih:....

⬇️ Starting Torrent Download...

info: Downloading metadata...
info: Connected to peers: 12
info: Progress: 15% (3.2 MB/s)
info: Progress: 52% (7.8 MB/s)
info: Progress: 100%
info: Downloaded: movie.mp4
```

---

## ⚠️ Notes
- Google Colab **no longer supports libtorrent**, so traditional torrent Python scripts do not work.
- This project uses the **WebTorrent engine** (works perfectly for movies, files, folders, etc).
- Large torrents depend on your Drive storage.

---

## 🙌 Contributions
Pull requests are welcome!

---
