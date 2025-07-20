# 🚀 GitHub Pages 部署完整操作指南

## 📋 **預備檢查**

在開始前，請確認：
- ✅ 您有 GitHub 帳戶
- ✅ 電腦已安裝 Git
- ✅ 專案檔案已準備完成

## 🔧 **第一步：建立 GitHub Repository**

### **方法一：透過 GitHub 網站**

1. **登入 GitHub**
   - 前往 https://github.com
   - 登入您的帳戶

2. **建立新 Repository**
   - 點擊右上角的 **"+"** 按鈕
   - 選擇 **"New repository"**

3. **Repository 設定**
   ```
   Repository name: api-security-research
   Description: 高科技製造業 API 安全研究專案
   Visibility: Public (GitHub Pages 免費版需要)
   
   ❌ 不要勾選 "Add a README file"
   ❌ 不要勾選 "Add .gitignore"  
   ❌ 不要勾選 "Choose a license"
   ```

4. **點擊 "Create repository"**

### **方法二：透過 GitHub CLI**
```bash
# 如果您有安裝 GitHub CLI
gh repo create api-security-research --public
```

## 💻 **第二步：準備本地專案**

### **在專案目錄執行**
```bash
# 1. 進入專案目錄
cd "/Users/chimin/Downloads/生成結果/API安全研究"

# 2. 初始化 Git repository
git init

# 3. 設定主分支名稱
git branch -M main

# 4. 添加檔案到 Git
git add .

# 5. 檢查狀態（確認 .gitignore 生效）
git status

# 應該看到：
# - ✅ index.html
# - ✅ *.html 檔案
# - ✅ assets/ 目錄
# - ✅ css/ 目錄
# - ✅ README.md
# - ❌ docs/ 目錄不會出現
# - ❌ 敏感 .md 檔案不會出現

# 6. 提交變更
git commit -m "🚀 Initial commit - API Security Research Project"
```

## 🔗 **第三步：連接到 GitHub**

```bash
# 替換 [YOUR_USERNAME] 為您的 GitHub 用戶名
git remote add origin https://github.com/[YOUR_USERNAME]/api-security-research.git

# 例如：
# git remote add origin https://github.com/john123/api-security-research.git
```

## ⬆️ **第四步：上傳到 GitHub**

```bash
# 推送檔案到 GitHub
git push -u origin main

# 如果出現認證提示，輸入您的 GitHub 用戶名和密碼/Token
```

## 🌐 **第五步：啟用 GitHub Pages**

### **透過 GitHub 網站設定**

1. **進入 Repository 設定**
   - 在您的 Repository 頁面
   - 點擊 **"Settings"** 選項卡

2. **找到 Pages 設定**
   - 在左側選單找到 **"Pages"**
   - 點擊進入

3. **配置 GitHub Pages**
   ```
   Source: Deploy from a branch
   Branch: main
   Folder: / (root)
   ```

4. **點擊 "Save"**

5. **等待部署**
   - GitHub 會顯示部署狀態
   - 通常需要 1-5 分鐘

6. **獲取網站 URL**
   ```
   您的網站將在以下位址上線：
   https://[YOUR_USERNAME].github.io/api-security-research/
   ```

## 📱 **第六步：驗證部署**

### **檢查項目**
- [ ] **首頁載入**：訪問主要 URL
- [ ] **導航功能**：測試下拉選單
- [ ] **頁面連結**：確認所有內部連結正常
- [ ] **圖片顯示**：Logo 和圖片正常載入
- [ ] **響應式**：手機版面正常
- [ ] **圖表功能**：ECharts 圖表正常渲染
- [ ] **安全檢查**：確認敏感檔案沒有出現

## 🔧 **常見問題解決**

### **問題 1：推送被拒絕**
```bash
# 如果遇到推送被拒絕，可能是認證問題
# 解決方案：使用 Personal Access Token

# 1. 前往 GitHub Settings > Developer settings > Personal access tokens
# 2. 生成新的 Token
# 3. 使用 Token 作為密碼
```

### **問題 2：頁面顯示 404**
```bash
# 檢查以下設定：
# 1. Repository 是否為 Public
# 2. GitHub Pages 設定是否正確
# 3. index.html 是否在根目錄
# 4. 等待 5-10 分鐘讓部署完成
```

### **問題 3：圖片或 CSS 無法載入**
```bash
# 檢查路徑是否正確：
# - 圖片：assets/images/cloudcorce-01.png
# - CSS：css/base.css
# - 所有路徑都應該是相對路徑
```

## 🎯 **成功部署確認**

當您看到以下畫面時，代表部署成功：

```
✅ 網站正常顯示
✅ Cloudforce Logo 出現
✅ 導航選單正常運作
✅ 所有頁面都能正常訪問
✅ 圖表和視覺效果正常
✅ 手機版面正常顯示
```

## 📋 **後續維護**

### **更新網站內容**
```bash
# 1. 修改檔案
# 2. 提交變更
git add .
git commit -m "Update content"
git push origin main

# 3. GitHub Pages 會自動重新部署
```

### **監控網站狀態**
- 定期檢查網站是否正常運行
- 監控外部 CDN（ECharts, Mermaid）狀態
- 根據使用者回饋調整內容

---

## 🎉 **完成！**

按照以上步驟，您就能成功將 API 安全研究專案部署到 GitHub Pages！

**預期結果**：
- 🌐 專業的線上網站
- 🔒 安全的檔案管理（敏感文件已排除）
- 📱 跨裝置相容
- ⚡ 快速載入速度

**需要協助？**
如果在操作過程中遇到問題，歡迎隨時詢問具體的錯誤訊息或狀況！