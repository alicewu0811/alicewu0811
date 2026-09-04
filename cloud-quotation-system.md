# 雲端報價單自動化系統

## Artifact 連結

**報價系統入口：** https://claude.ai/code/artifact/f0281e25-7588-452e-b590-12992f8ddac7

業務同事用 claude.ai 帳號開啟上方連結即可使用。

## 功能

- 填入客戶名稱、雲端服務品項（AWS / GCP / 騰訊雲 / Azure / GA 全球加速服務）、折扣/加成
- 即時預覽報價單
- 一鍵下載 HTML 報價單（瀏覽器開啟後列印為 PDF）
- 一鍵建立 Asana 任務（專案 ID：`1205579410756702`，Section：雲端報價單）

## 前置需求

使用者需在 claude.ai 完成以下設定：

1. 登入 claude.ai 帳號
2. Settings → Connectors → 連接 Asana（才能使用自動建立任務功能）

## 報價單標準格式

### 預設品項

| 品項 | 適用平台 |
|------|----------|
| AWS | Amazon Web Services (AWS) |
| GCP | Google Cloud Platform (GCP) |
| 騰訊雲 | Tencent Cloud（騰訊雲） |
| Azure | Microsoft Azure |
| GA 全球加速服務 | Global Accelerator（GA 全球加速服務） |

### 標準條款（5 條）

1. 「服務項目」中所載明之服務內容與價格，將由雙方另行議定。
2. 本報價單內容為本公司商業機密，雙方均負保密義務，並應遵守中華民國法律及本公司合約規範。
3. 本報價單有效期限為 7 日，逾期需重新確認報價。
4. 專業服務項目與付款條件等細節，均以正式合約文件內容為準執行。
5. 本報價單經客戶用印回傳後，即視為正式訂單成立。

### 預設稅務行

營業稅（5%）

## 對話式報價（原有 Skill）

除了 Artifact 網頁表單，也可以直接在 Claude Code 對話中說：

- 「幫我做一份報價單，客戶：XXX，品項：AWS，折扣：85折」
- 「開一張 GCP 的報價單」

這會觸發 `cloud-quotation` Skill，自動產生 Word + PDF 並建立 Asana 任務。

## Asana 任務格式

- **任務名稱：** `報價單 — [客戶名稱]｜[品項] [折扣/加成]`
- **專案：** `1205579410756702`
- **Section：** `1205579410756703`（雲端報價單）
- **到期日：** 報價當天
