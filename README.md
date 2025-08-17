[Uploading README.md…]()

# 靈性修養問卷生成與分析系統

## 系統概述

本系統是一個完整的靈性修養問卷生成與分析平台，由孫效智教授編制，臺大生命教育研發育成中心暨為愛前行基金會開發。系統提供問卷編輯、題庫管理、問卷作答和數據收集等完整功能。

### 主要特色

- 🎯 **雙版本支持**：支援初篩版（5分鐘內完成）和完整版（12-15分鐘完成）
- 📊 **四層分類架構**：靈性修養七面向、靈性健康十核心指標、靈修七原則、日常靈修實踐
- 🔄 **智能題目管理**：支援拖曳排序、隨機排列、分類篩選
- 📱 **響應式設計**：完美適配桌面、平板和手機設備
- ☁️ **雲端整合**：與Google Sheets無縫整合，實現數據持久化
- 🔒 **隱私保護**：完整的同意書流程和數據保護機制

## 系統架構

### 頁面結構

```
├── index.html          # 問卷編輯與管理頁面
├── survey.html         # 問卷作答頁面
└── README.md          # 系統說明文件
```

### 功能模組

#### 頁面1：問卷編輯與管理 (`index.html`)

**左側邊欄 - 分類管理**
- ✅ 四層分類架構管理
- ✅ 新增/修改/刪除分類功能
- ✅ 題庫數量統計顯示
- ✅ 可收合的側邊欄設計

**主要功能區**
- ✅ 新增題目（支援初篩版/完整版選擇）
- ✅ 題目類型區分（共通題/宗教信仰者專屬題）
- ✅ 題庫管理（查看、編輯、刪除、拖曳排序）
- ✅ 問卷預覽（含隨機排序功能）
- ✅ 題庫匯出（HTML格式，包含管理序號和隨機序號）

#### 頁面2：問卷作答 (`survey.html`)

**作答流程**
1. **引導頁面**：系統介紹和使用說明
2. **同意書**：詳細的研究說明和隱私保護條款
3. **基本資料**：11項個人背景資訊收集
4. **問卷作答**：智能題目呈現（根據宗教信仰自動調整）
5. **完成頁面**：感謝頁面和後續說明

## 部署指南

### GitHub Pages 部署

1. **創建 GitHub 倉庫**
   ```bash
   # 創建新倉庫
   git init
   git add .
   git commit -m "Initial commit: 靈性修養問卷系統"
   git branch -M main
   git remote add origin https://github.com/你的用戶名/spiritual-survey-system.git
   git push -u origin main
   ```

2. **啟用 GitHub Pages**
   - 進入倉庫設置 (Settings)
   - 找到 "Pages" 選項
   - Source 選擇 "Deploy from a branch"
   - Branch 選擇 "main"
   - Folder 選擇 "/ (root)"
   - 點擊 "Save"

3. **訪問網站**
   - 部署完成後，系統將可通過以下網址訪問：
   - `https://你的用戶名.github.io/倉庫名稱/`

### 本地開發環境

```bash
# 克隆倉庫
git clone https://github.com/你的用戶名/spiritual-survey-system.git
cd spiritual-survey-system

# 使用 Python 啟動本地服務器
python -m http.server 8000

# 或使用 Node.js
npx http-server

# 訪問 http://localhost:8000
```

## 使用指南

### 管理員操作流程

#### 1. 建立分類架構
- 點擊左側邊欄「新增分類」
- 系統已預設四大主分類和相關子分類
- 可根據需要新增自定義分類

#### 2. 新增問卷題目
- 填寫題目內容
- 選擇所屬分類
- 選擇問卷版本（初篩版/完整版/兩者皆有）
- 選擇題目類型（共通題/宗教信仰者專屬題）
- 系統會自動儲存並同步至雲端

#### 3. 管理題庫
- 使用「查看所有題庫」功能瀏覽所有題目
- 支援分類和版本篩選
- 可拖曳題目改變順序
- 點擊編輯按鈕修改題目內容
- 點擊刪除按鈕移除題目

#### 4. 預覽問卷
- 使用「問卷預覽」查看受試者視角
- 「隨機排序」功能可打亂題目順序
- 預覽包含完整的評分說明

#### 5. 匯出題庫
- 點擊「匯出題庫」生成HTML文件
- 文件包含管理序號和隨機序號對照
- 便於後續數據分析和比對

### 受試者操作流程

#### 1. 系統介紹
- 閱讀引導語了解靈性健康概念
- 查看問卷說明和預估時間

#### 2. 同意書確認
- 詳細閱讀研究目的和資料使用說明
- 確認同意參與研究

#### 3. 填寫基本資料
- 完整填寫11項個人背景資訊
- 系統會根據宗教信仰自動調整後續題目

#### 4. 問卷作答
- 根據1-6分量表進行評分
- 系統會顯示作答進度
- 有宗教信仰者需回答額外的專屬題目

#### 5. 提交完成
- 確認所有題目已回答
- 提交後顯示感謝頁面

## 技術規格

### 前端技術
- **HTML5**：語義化標記和現代Web標準
- **CSS3**：Tailwind CSS框架，響應式設計
- **JavaScript (ES6+)**：現代JavaScript特性
- **Font Awesome**：圖標庫
- **SortableJS**：拖曳排序功能

### 數據存儲
- **LocalStorage**：本地數據持久化
- **Google Sheets API**：雲端數據同步
- **自動備份**：每5分鐘自動同步至雲端

### 瀏覽器支持
- Chrome 60+
- Firefox 55+
- Safari 12+
- Edge 79+

### 響應式斷點
- 手機：< 768px
- 平板：768px - 1024px
- 桌面：> 1024px

## 數據結構

### 分類數據格式
```javascript
{
  id: "category-id",
  name: "分類名稱",
  parent: "parent-id" | null,
  questionCount: 0
}
```

### 題目數據格式
```javascript
{
  id: "question-id",
  text: "題目內容",
  category: "category-id",
  version: "both" | "screening" | "full",
  type: "common" | "religious",
  order: 0
}
```

### 問卷回答格式
```javascript
{
  personalInfo: {
    name: "姓名",
    birthYear: "年",
    birthMonth: "月",
    birthDay: "日",
    gender: "性別",
    nationality: "國籍",
    city: "居住城市",
    occupation: "職業",
    education: "教育程度",
    maritalStatus: "婚姻狀況",
    religion: "宗教信仰",
    livingStatus: "居住狀況",
    testDate: "檢測日期"
  },
  answers: {
    "question-id": 1-6
  },
  hasReligion: boolean,
  submissionTime: "ISO timestamp"
}
```

## Google Sheets 整合

### API 端點
```
https://script.google.com/macros/s/AKfycbzDheXToz7fvt5Pv3zYWWsQsi1PxHvSCk2vEkGB2UFWWVjl2KrWklSUftRJgAkTRuhWTA/exec
```

### 支援操作
- `saveQuestionBank`：儲存題庫數據
- `submitSurvey`：提交問卷回答

### 數據同步機制
- 自動儲存：輸入變更後1秒自動儲存至本地
- 雲端同步：每5分鐘自動同步至Google Sheets
- 手動同步：題目新增/修改時立即同步

## 安全性與隱私

### 數據保護措施
- 所有個人資料僅用於學術研究
- 研究結果以匿名方式呈現
- 完整的同意書流程
- 參與者可隨時退出研究

### 技術安全
- 使用HTTPS加密傳輸
- 本地數據加密存儲
- 無絕對路徑依賴，確保部署安全性

## 常見問題

### Q: 如何修改Google Sheets API端點？
A: 在兩個HTML文件中搜尋`GOOGLE_SCRIPT_URL`變數並替換為新的端點。

### Q: 如何自定義分類架構？
A: 修改`index.html`中的`defaultCategories`陣列，或使用界面直接新增分類。

### Q: 如何備份數據？
A: 使用瀏覽器開發者工具導出LocalStorage數據，或從Google Sheets下載備份。

### Q: 系統支援多語言嗎？
A: 目前僅支援繁體中文，如需其他語言需要修改HTML文件中的文字內容。

### Q: 如何自定義評分量表？
A: 修改JavaScript中的評分相關函數，包括`getScaleText()`和評分選項生成邏輯。

## 更新日誌

### v1.0.0 (2024-08-17)
- ✅ 完整的問卷編輯和管理功能
- ✅ 響應式問卷作答界面
- ✅ Google Sheets雲端整合
- ✅ 四層分類架構支援
- ✅ 雙版本問卷支援
- ✅ 完整的隱私保護機制

## 技術支援

如有技術問題或建議，請聯繫：
- 編制者：孫效智教授
- 編制單位：臺大生命教育研發育成中心暨為愛前行基金會

## 授權條款

本系統僅供學術研究使用，請勿用於商業用途。使用本系統請註明出處和編制單位。

---

**最後更新：2024年8月17日**
