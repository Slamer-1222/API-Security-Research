# .gitignore 使用指南

## 🎯 針對本專案的 .gitignore 使用

### 📁 當前專案結構
```
專案目錄/
├── .gitignore                          # ✅ 已建立
├── README.md                           # ✅ 會被上傳
├── index.html                          # ✅ 會被上傳
├── [其他 HTML 檔案]                     # ✅ 會被上傳  
├── assets/images/                      # ✅ 會被上傳
├── css/                               # ✅ 會被上傳
├── docs/                              # ❌ 會被忽略
├── GITHUB_PAGES_DEPLOYMENT.md         # ❌ 會被忽略
└── DEPLOYMENT_SECURITY_GUIDE.md       # ❌ 會被忽略
```

### 🛠️ 實施步驟

#### **第一步：確認 .gitignore 已建立**
檢查專案根目錄是否有 `.gitignore` 檔案

#### **第二步：測試忽略效果**
```bash
# 在專案目錄執行
git status

# 應該看到類似結果：
# On branch main
# Untracked files:
#   .gitignore
#   README.md
#   index.html
#   api_trends.html
#   assets/
#   css/
# 
# 注意：docs/ 和 *.md 開發文件不會出現
```

#### **第三步：提交設定**
```bash
# 1. 添加 .gitignore
git add .gitignore
git commit -m "Add .gitignore to exclude sensitive files"

# 2. 添加網站核心檔案
git add .
git commit -m "Add website core files for GitHub Pages"

# 3. 推送到 GitHub
git push origin main
```

### 📊 **忽略效果對照**

| 檔案/目錄 | 狀態 | 說明 |
|-----------|------|------|
| `index.html` | ✅ 上傳 | 網站首頁 |
| `*.html` | ✅ 上傳 | 所有網頁檔案 |
| `assets/` | ✅ 上傳 | 圖片和資源 |
| `css/` | ✅ 上傳 | 樣式檔案 |
| `README.md` | ✅ 上傳 | 專案說明 |
| `docs/` | ❌ 忽略 | 包含敏感技術文件 |
| `GITHUB_PAGES_DEPLOYMENT.md` | ❌ 忽略 | 部署指南 |
| `PROJECT_*.md` | ❌ 忽略 | 專案開發文件 |

### 🔍 **驗證方法**

#### **方法一：使用 git status**
```bash
git status --ignored

# 正常輸出應該顯示：
# Ignored files:
#   docs/
#   GITHUB_PAGES_DEPLOYMENT.md
#   DEPLOYMENT_SECURITY_GUIDE.md
```

#### **方法二：檢查特定檔案**
```bash
# 檢查敏感檔案是否被忽略
git check-ignore docs/PROJECT_STATUS_REPORT.md
# 如果被忽略，會輸出檔案路徑

git check-ignore index.html
# 如果沒被忽略，不會有輸出
```

#### **方法三：查看 GitHub Repository**
上傳後檢查 GitHub 上的檔案清單，確認敏感檔案沒有出現。

### ⚠️ **常見問題與解決**

#### **問題：檔案已經被 Git 追蹤了怎麼辦？**
```bash
# 如果敏感檔案已經在 Git 中，需要先移除
git rm --cached docs/PROJECT_STATUS_REPORT.md
git rm --cached GITHUB_PAGES_DEPLOYMENT.md

# 移除整個目錄
git rm --cached -r docs/

# 提交移除操作
git commit -m "Remove sensitive files from Git tracking"
```

#### **問題：.gitignore 不生效？**
```bash
# 1. 檢查檔名是否正確（前面要有點）
ls -la | grep gitignore

# 2. 檢查檔案內容
cat .gitignore

# 3. 清除 Git 快取並重新加入
git rm -r --cached .
git add .
git commit -m "Apply .gitignore rules"
```

### 🎯 **最終確認**

完成設定後，您的 GitHub Pages 將只包含：
- ✅ 網站核心檔案（HTML、CSS、圖片）
- ✅ 簡化的 README.md  
- ❌ 無任何敏感的技術文件
- ❌ 無開發過程記錄

這樣既保持了功能完整性，又確保了安全性！

---
**安全等級**: 🔒 高  
**實施難度**: 📝 簡單  
**維護需求**: 🔄 自動化