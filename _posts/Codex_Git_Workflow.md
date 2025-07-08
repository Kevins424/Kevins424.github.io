# 🧠 Codex + Git 協作開發流程教學

這份教學適合在使用 VS Code + GitHub Copilot Chat（Codex）進行功能開發、測試與 Pull Request 流程中使用，幫助你更有效率地上板並維持團隊協作品質。

---

## 🎯 使用場景

當你開發一個新功能，例如「使用者登入頁」，希望：

- 實作功能
- 撰寫單元測試
- 撰寫良好 commit 與 PR 描述
- 讓 Codex 協助減少出錯與加速效率
- 提出高品質 Pull Request（PR）

---

## 🔁 開發流程步驟

### 1️⃣ 拉取主分支並建立 Feature 分支

```bash
git checkout main
git pull origin main
git checkout -b feature/login-page
```

> ✅ 分支命名建議：`feature/xxx`、`fix/xxx`、`chore/xxx`

---

### 2️⃣ 使用 Codex 協助開發

開啟 VS Code → Codex Chat 面板，請求支援：
- ✅ 功能邏輯設計建議
- ✅ 單元測試撰寫（Jest, Mocha 等）
- ✅ ESLint 錯誤修正建議
- ✅ 加上 JSDoc 或清楚註解

例如：

> 💬「請幫我補上這段函式的 JSDoc 註解」  
> 💬「幫我寫個 login 驗證的 Jest 測試」  
> 💬「這段程式是否有 race condition？」  

---

### 3️⃣ Commit 良好訊息

使用語義化 commit 規範：

```bash
git add .
git commit -m "feat: add login page with form validation"
```

| Prefix | 用途 |
|--------|------|
| `feat` | 新功能 |
| `fix` | 修 bug |
| `refactor` | 重構無行為改變 |
| `test` | 加測試 |
| `docs` | 文件更新 |
| `chore` | 雜項調整 |

---

### 4️⃣ 本地測試與自檢

執行：

```bash
npm run lint
npm run test
```

Codex 可協助檢查：
- ✅ 邏輯正確性
- ✅ 測試覆蓋率建議
- ✅ 潛在異常或錯誤場景是否補測

---

### 5️⃣ Push 分支並建立 PR

```bash
git push origin feature/login-page
```

前往 GitHub 建立 PR，選擇：
- Base: `main`
- Compare: `feature/login-page`

---

### 6️⃣ 撰寫清楚 PR 描述

你可以請 Codex 幫你整理一份清晰的 PR 模板，如：

```markdown
### 📌 功能簡介
新增使用者登入頁面，支援 email/password 驗證與錯誤提示。

### ✅ 完成項目
- 登入表單介面（React）
- 表單驗證功能
- 對應單元測試

### 🧪 測試方式
- 手動操作登入流程（含錯誤情境）
- Jest 單元測試通過
- Lint 無錯誤
```

---

### 7️⃣ 處理 Review 與 Merge

- 回應 reviewer 留言，可請 Codex 幫你潤飾回覆
- 若需 rebase：

```bash
git fetch origin
git rebase origin/main
# 解衝突後繼續
git push --force
```

---

### 8️⃣ 合併 PR 並清理分支

合併成功後清理本機分支：

```bash
git checkout main
git pull origin main
git branch -d feature/login-page
```

---

## 🧠 Codex 在流程中能幫你什麼？

| 階段 | Codex 可協助 |
|------|--------------|
| 規劃階段 | 功能拆解、設計草圖、程式架構建議 |
| 開發階段 | 補程式碼、找 bug、寫測試 |
| 提交階段 | 撰寫 commit 訊息、PR 描述、釐清改動內容 |
| Review 階段 | 解釋 reviewer 留言、產生修正建議 |
| Merge 後 | 協助記錄變更、補文件 |

---

## 📦 建議搭配工具

| 工具 | 用途 |
|------|------|
| ESLint + Prettier | 格式統一與錯誤提示 |
| Husky | Pre-commit 檢查 |
| Jest / Mocha | 單元測試 |
| GitHub Copilot Chat | AI 協作助手（即 Codex） |
| Conventional Commits | 提高 commit 可讀性與 changelog 自動化 |

---

## 📝 總結

這份 Codex + Git 協作流程適用於：

- 單人開發想自我提升質量
- 團隊開發維護 PR 紀律
- 想結合 AI 工具寫出穩健、專業的代碼流程

建議可將這套流程納入你的 `.github/CONTRIBUTING.md` 或 README 之中！
