# BPB-Auto-update-and-obfuscate

自動同步並混淆 BPB-Worker-Panel 倉庫下的Releases最新 `worker.js` 文件。

[EN](Readme.md)|[简体中文](Readme.Chinese_Simplified.md)|**繁體中文**  

## 🚀 快速開始（不建議直接Fork運行，推薦私有倉庫部署。）

1. 使用git clone命令/Download zip獲取源文件。
2. 創建一個私有倉庫並提交本倉庫的文件。
3. [如果你此前並未啓動過GitHub Actions功能] 進入 Actions 頁面，點擊 **Enable workflows**（啓用 GitHub Actions）。
4. 無需其他配置，GitHub 默認的 `GITHUB_TOKEN` 權限即可推送更新。
5. 你可以手動點擊 **Run workflow**，也可以等待每天定時自動檢查。

> 注意：確保你的倉庫默認分支爲 main，否則推送時可能失敗。

🌟 如果覺得這個項目對你有幫助，歡迎順手點個 Star 支持一下！

---

## 功能介紹

- 每天自動檢查 `bia-pain-bache/BPB-Worker-Panel` 倉庫的最新 Release
- 自動下載最新版本的 worker.js 並重命名爲origin.js
- 混淆後重命名爲 `_worker.js`
- 同步更新本地 `version.txt`
- 自動提交併推送到本倉庫

## 工作流程

GitHub Actions 會每日 00:00（UTC 時間）自動運行：

1. 獲取上游倉庫的最新 Release 版本號
2. 比較本地 `version.txt` 的記錄
3. 自動下載，混淆，並替換 `_worker.js`
4. 更新 `version.txt`
5. 自動提交併推送到主分支（main）

---

## 📂 目錄結構

```
/
├── `_worker.js`   
├── origin.js         
├── `version.txt`        
├── LICENSE            
├── .gitignore         
├── Readme.md
├── Readme.Chinese_Simplified.md
├── Readme.Chinese_Traditional.md
└── .github/
    └── workflows/
        └── update_worker.yml
```

---

## ⚙️ 配置說明

- 無需手動設置 Token：默認使用 GitHub 提供的 `GITHUB_TOKEN` 進行權限認證。
- 如需修改同步源：編輯 `.github/workflows/update_worker.yml`，修改源倉庫地址即可。

---

## 📜 開源協議

本項目使用 MIT License 開源。

您可以自由地使用、複製、修改和分發本項目，前提是附帶原始許可證聲明。

---

## 📢 特別說明

- 本倉庫同步的內容來源於 [BPB-Worker-Panel](https://github.com/bia-pain-bache/BPB-Worker-Panel)。
- GitHub Workflows的源碼及編寫參考了 [GitHub@byJoey/wk-Auto-update](https://github.com/byJoey/wk-Auto-update) 和 Hans漢斯.
- 原項目版權歸原作者所有，本項目僅用於自動同步更新。
