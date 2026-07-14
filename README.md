# Premium DevInsight Blog (Astro)

這是一個基於 **Astro 5** 打造的高效能、極致 SEO 優化個人部落格與技術顧問網站。

## ✨ 特色功能

*   **頂尖 SEO**：使用 Astro 的靜態頁面生成 (SSG) 與輕量化 HTML 輸出，搭配自動 Sitemap 與 RSS 訂閱生成。
*   **優雅設計**：Vanilla CSS 實現的現代毛玻璃鏡面（Glassmorphism）美學，完美支援系統級自動暗黑模式。
*   **效能優化 (Lighthouse 100/100)**：
    *   **優化 YouTube 外嵌**：內建 `<LiteYoutube />` 組件，延遲載入影片 iframe，防止第三方 JS 拖慢網頁速度。
*   **線上諮詢預約**：整合 **Cal.com** 的預約元件（包含一對一諮詢的模擬體驗與生產環境部署指引）。
*   **金流收款整合**：整合 **Stripe Checkout** 收款介面（支援台灣信用卡/台幣結帳、免公司登記個人戶指引）。
*   **套件管理器**：使用 `pnpm` 鎖定依賴，極速建置且不污染全域環境。

---

## 🚀 專案目錄結構

```text
├── src/
│   ├── assets/       # 圖片、字型等靜態資源
│   ├── components/   # BaseHead, Header, Footer, 以及 LiteYoutube 組件
│   ├── content/      # Markdown / MDX 部落格文章管理
│   ├── layouts/      # BlogPost.astro 頁面排版
│   └── pages/        # 頁面路由 (首頁, 部落格, 預約, 付費, 關於我)
├── pnpm-workspace.yaml # pnpm v11 建置與快取白名單設定
├── astro.config.mjs
└── tsconfig.json
```

---

## 🛠️ 開發與建置指令

專案推薦使用 `pnpm` 進行管理，以維持環境純淨。

| 指令 | 說明 |
| :--- | :--- |
| `pnpm install` | 安裝專案所有依賴套件（已自動授權 esbuild & sharp 建置腳本） |
| `pnpm run dev` | 啟動本地開發伺服器（預設為 `http://localhost:4321`） |
| `pnpm run build` | 進行生產環境靜態頁面建置（輸出至 `/dist`） |
| `pnpm run preview` | 本地預覽生產環境建置結果 |

---

## 🔗 線上整合指引

### 1. Cal.com 線上預約
預約頁面位於 `src/pages/booking.astro`。目前為模擬演示模式，上線時請依據該頁面底部的 **工程師整合說明** 替換為您的 Cal.com 帳號連結。

### 2. Stripe 金流付款
方案與付費頁面位於 `src/pages/pricing.astro`。目前為模擬 Stripe Checkout 付款安全驗證。上線時請註冊 Stripe 個人帳戶，並在後端 Serverless API（如 Cloudflare Workers）中串接 Stripe Session Redirect（可參考該頁面底部的 **後端整合代碼** 範例）。

---

## 📦 部署與 CI/CD (Cloudflare Pages)

專案已準備好與 **Cloudflare Pages** 進行整合。
1. 將此專案關聯至您的 GitHub 儲存庫 `blog`。
2. 每次 `git push origin main` 都會自動在 Cloudflare 進行構建並分發至全球邊緣網路。
3. 建議透過 Cloudflare Registrar 註冊/指向您的專案網域，以獲得最頂尖的載入速度。
