# BPB-Auto-update-and-obfuscate

Automatically sync and obfuscate the latest `worker.js` file from the Releases of the BPB-Worker-Panel repository.

**EN**|[简体中文](Readme.Chinese_Simplified.md)|[繁體中文](Readme.Chinese_Traditional.md)

## 🚀 Quick Start (Direct Fork execution not recommended; private repository deployment is advised.)

1. Use `git clone` or "Download ZIP" to obtain the source files.
2. Create a private repository and upload the files from this repository.
3. [If you haven’t previously enabled GitHub Actions] Go to the Actions page and click **Enable workflows**.
4. No further configuration needed—GitHub’s default `GITHUB_TOKEN` permission is sufficient for pushing updates.
5. You can manually click **Run workflow**, or wait for the daily scheduled check.

> Note: Make sure your repository’s default branch is `main`, otherwise pushing may fail.

🌟 If you find this project helpful, feel free to give it a Star to show your support!

---

## Features

- Automatically checks the latest Release of the `bia-pain-bache/BPB-Worker-Panel` repository daily.
- Automatically downloads the latest `worker.js` and renames it to `origin.js`.
- Obfuscates the file and renames it to `_worker.js`.
- Updates the local `version.txt`.
- Automatically commits and pushes to this repository.

## Workflow

GitHub Actions runs automatically every day at 00:00 UTC:

1. Fetch the latest Release version number from the upstream repository.
2. Compare it with the version recorded in the local `version.txt`.
3. Automatically download, obfuscate, and replace `_worker.js`.
4. Update `version.txt`.
5. Automatically commit and push to the `main` branch.

---

## 📂 Directory Structure

```
/
├── _worker.js   
├── origin.js         
├── version.txt        
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

## ⚙️ Configuration Notes

- No need to manually set a token: uses GitHub’s default `GITHUB_TOKEN` for permission authentication.
- To modify the sync source: edit `.github/workflows/update_worker.yml` and change the source repository address.

---

## 📜 License

This project is open-sourced under the MIT License.

You are free to use, copy, modify, and distribute this project as long as the original license notice is included.

---

## 📢 Special Notes

- The content synchronized by this repository comes from [BPB-Worker-Panel](https://github.com/bia-pain-bache/BPB-Worker-Panel).
- The source code and setup of GitHub Workflows were referenced from [GitHub@byJoey/wk-Auto-update](https://github.com/byJoey/wk-Auto-update) and Hans汉斯.
- All copyrights belong to the original author. 
  This project is intended solely for automatic synchronization and updates.
