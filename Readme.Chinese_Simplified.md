# BPB-Auto-update-and-obfuscate

自动同步并混淆 BPB-Worker-Panel 仓库下的Releases最新 `worker.js` 文件。

[EN](Readme.md)|**简体中文**|[繁體中文](Readme.Chinese_Traditional.md) 

## 🚀 快速开始（不建议直接Fork运行，推荐私有仓库部署。）

1. 使用git clone命令/Download zip获取源文件。
2. 创建一个私有仓库并提交本仓库的文件。
3. [如果你此前并未启动过GitHub Actions功能] 进入 Actions 页面，点击 **Enable workflows**（启用 GitHub Actions）。
4. 无需其他配置，GitHub 默认的 `GITHUB_TOKEN` 权限即可推送更新。
5. 你可以手动点击 **Run workflow**，也可以等待每天定时自动检查。

> 注意：确保你的仓库默认分支为 main，否则推送时可能失败。

🌟 如果觉得这个项目对你有帮助，欢迎顺手点个 Star 支持一下！

---

## 功能介绍

- 每天自动检查 `bia-pain-bache/BPB-Worker-Panel` 仓库的最新 Release
- 自动下载最新版本的 worker.js 并重命名为origin.js
- 混淆后重命名为 `_worker.js`
- 同步更新本地 `version.txt`
- 自动提交并推送到本仓库

## 工作流程

GitHub Actions 会每日 00:00（UTC 时间）自动运行：

1. 获取上游仓库的最新 Release 版本号
2. 比较本地 `version.txt` 的记录
3. 自动下载，混淆，并替换 `_worker.js`
4. 更新 `version.txt`
5. 自动提交并推送到主分支（main）

---

## 📂 目录结构

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

## ⚙️ 配置说明

- 无需手动设置 Token：默认使用 GitHub 提供的 `GITHUB_TOKEN` 进行权限认证。
- 如需修改同步源：编辑 `.github/workflows/update_worker.yml`，修改源仓库地址即可。

---

## 📜 开源协议

本项目使用 MIT License 开源。

您可以自由地使用、复制、修改和分发本项目，前提是附带原始许可证声明。

---

## 📢 特别说明

- 本仓库同步的内容来源于 [BPB-Worker-Panel](https://github.com/bia-pain-bache/BPB-Worker-Panel)。
- GitHub Workflows的源码及编写参考了 [GitHub@byJoey/wk-Auto-update](https://github.com/byJoey/wk-Auto-update) 和 Hans汉斯.
- 原项目版权归原作者所有，本项目仅用于自动同步更新。
